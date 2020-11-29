This page describes how level and maker codes are generated in the Super Mario Maker games.

When a level file is uploaded or a new user is registered the server gives it a unique data or user id. The level or maker code entirely depends on the data or user id: if two levels were given the same data id they would also have the same level code.

## Super Mario Maker
In the original Super Mario Maker game, a level code consists of four fields separated by dashes, each of which consists of four uppercase hex digits. For example: `77A9-0000-003D-1D4F`.

The second field is easy: it always consists of zeros.

The last two fields contain the data id that was generated when the level was uploaded. In this case: `0x3D1D4F = 4005199`.

The first field contains a checksum that depends on the data id. Interestingly, the game uses the function that calculates the signature of a [PRUDP V0](PRUDP-Protocol.md#v0-format) packet here. This function basically returns the first four bytes of a HMAC-MD5 in reversed byte order, where the key is the MD5 hash of the [access key](Game-Server-List.md). In this case, the HMAC is calculated over the 8-byte data id in little endian byte order. To combine the checksum with the data id, the two most significant bytes are inserted into the first field of the level code. Because the the checksum was returned in little endian byte order, this is actually the same as the third and fourth byte of the HMAC in reversed order.

To make this clear, let's walk through the checksum algorithm step by step:
1. The access key of Super Mario Maker is `9f2b4678`.
2. The MD5 hash of the string `9f2b4678` is `9ce21c9e046e85f0cf6ca00d1eaaaf5f`. This is the key we will feed into the HMAC algorithm.
3. If we transform the course id into an 8-byte little endian number we get: `4f1d3d0000000000`.
4. The HMAC of `4f1d3d0000000000` with the key `9ce21c9e046e85f0cf6ca00d1eaaaf5f` is `2417a977a502a3eba4d9d971e10c06c5`.
5. Now we take the third and fourth byte (`A9` and `77`), reverse their order, and we get `77A9`, which is exactly what we were expecting.

In Python, this could be implemented like this:

```python
>>> import struct
>>> import hashlib
>>> import hmac
>>> key = hashlib.md5(b"9f2b4678").digest()
>>> data = struct.pack("<Q", 0x3D1D4F)
>>> checksum = hmac.HMAC(key, data).digest()
>>> checksum[3:1:-1].hex().upper()
'77A9'
```

## Super Mario Maker 2
In Super Mario Maker 2, the algorithm and format of level and maker codes was completely changed. Now, a level or maker code consists of three fields separated by dashes, each of which consists of three uppercase letters and digits. For example: `2J5-3K2-Y9G`.

A code may consist of all digits and letters except for A, E, I, O, U and Z. This leaves the following 30 characters: `0123456789BCDFGHJKLMNPQRSTVWXY`.

To obtain the data or user id from a level/maker code one must first convert it to binary form: remove the dashes, reverse the order of the characters and calculate the number in base 30.

```python
>>> charset = "0123456789BCDFGHJKLMNPQRSTVWXY"
>>> code = "2J5-3K2-Y9G".replace("-", "")[::-1]
>>> number = 0
>>> for char in code:
	number = number * 30 + charset.index(char)

	
>>> bin(number)[2:]
'10001000110101101000010011111001000101101110'
```

This binary number can be split up into the following fields:

```
 A     B             C           D E      F
1000 100011 01011010000100111110 0 1 000101101110
```

Fields A and E always contain `1000` and `1` respectively. Field D is always `0` in a level code and `1` in a maker code.

The data/user id can be obtained from field C and field F as follows:
1. Concatenate field F and field C. In our example, this gives `00010110111001011010000100111110`.
2. Apply an XOR with `00010110100000001110000001111100`. This gives `00000000011001010100000101000010` in our example.
3. Convert the number back to decimal: the data id of the example code is 6635842.

Field B contains a simple checksum: `(id - 31) % 64`. In our example, this would be `(6635842 - 31) % 64 = 35`, which is `100011` in binary.
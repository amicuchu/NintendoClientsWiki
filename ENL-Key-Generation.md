ENL is a first-party networking framework on top of [PIA](PIA-Overview) and [NEX](NEX-Overview-(Game-Servers)). To generate a key ENL uses the random number generator provided by SEAD (Nintendo's private standard library).

The random number generator works as follows:
```python
class Random:
    def __init__(self, seed):
        multiplier = 0x6C078965
        
        temp = seed
        self.state = []
        for i in range(1, 5):
            temp ^= temp >> 30
            temp = (temp * multiplier + i) & 0xFFFFFFFF
            self.state.append(temp)
    
    # Returns a random 32-bit integer
    def u32(self):
        temp = self.state[0]
        temp = (temp ^ (temp << 11)) & 0xFFFFFFFF
        temp ^= temp >> 8
        temp ^= self.state[3]
        temp ^= self.state[3] >> 19
        self.state[0] = self.state[1]
        self.state[1] = self.state[2]
        self.state[2] = self.state[3]
        self.state[3] = temp
        return temp
    
    # Returns a random integer smaller than 'max'
    def uint(self, max):
        return (self.u32() * max) >> 32
```

The game passes a `sead::Random` instance and a table of 32-bit integers to ENL. For each byte in the key ENL generates two random numbers: an index into the provided table and a 'byte index' or shift amount. ENL always generates 4 bytes at once and stores them into the key in little endian byte order. In Python, this could look as follows:
```python
# Generates 4 bytes of the key and
# returns them as an integer
def create_key_part(rand, table):
    value = 0
    for i in range(4):
        index = rand.uint(len(table))
        shift = rand.uint(4) * 8
        byte = (table[index] >> shift) & 0xFF
        value = (value << 8) | byte
    return value

# Generates a key with the given random
# number generator and integer table
def create_key(rand, table, size):
    if size % 4:
        raise ValueError("Key size must be multiple of 4")
    
    key = b""
    for i in range(size // 4):
        value = create_key_part(rand, table)
        key += struct.pack("<I", value) #Little endian
    return key
```

## Spatoon 2
To generate its [LAN key](LAN-Protocol), Splatoon 2 constructs a random number generator with the seed `0xCEB9D8D9` and it uses the following integer table:
```python
table = [
    0x56CB956F, 0x7B50EEC6, 0x234D1A63, 0x1C691A6B,
    0xD2D9C482, 0xCFE21965, 0x0B32DF99, 0xB32AFE44,
    0xB15DA3D7, 0x86588505, 0x4FC8CD8B, 0xC30F864B,
    0x08D4D3BE, 0xEFDEC6CA, 0x63A1D53F, 0xC545538D,
    0x715E27A2, 0x4818A005, 0x8C28D9F8, 0xC303EABF,
    0xF1D847ED, 0xE837F303, 0xE68981E8, 0x63E2F9BC,
    0xC320F7E1, 0x5E0B4084, 0x502B2A2D, 0x65D36579,
    0x0D169E46, 0x65AB445D, 0xFDF0678B, 0x26167D3E,
    0xFE5025A0, 0x04EB0EA8, 0xC048B044, 0xF858002E,
    0x6725F7D6, 0xD4086AA8, 0xF216DE10, 0x0F1807E6,
    0xD3614878, 0x34A2FEE6, 0xA69AE3DE, 0xED8518EF,
    0x6FCCB7A5, 0x7F8D0E40, 0x9B72BFA8, 0x87C669D4,
    0x5BF80652, 0x9A71383F, 0xBA3E7A7A, 0x1ABA65A3,
    0xA9A16DFF, 0xD07B9E3C, 0x11C9BD45, 0xF14A6D81,
    0x78516ECD, 0x53445C15, 0xC86E9942, 0x5501D2C9,
    0xD0D4ECB3, 0x38F5C341, 0xC4A16155, 0x42F1F406
]
```

Given the code snippets above, the following lines would generate the key for Splatoon 2:
```python
rand = Random(0xCEB9D8D9)
key = create_key(rand, table, 16)
print(key.hex())
```

Which should print the following key: `ee182a63e216cdb1f51ad4bed8cf6508`
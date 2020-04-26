## [[Server List]] > Ninja Server

The ninja server provides an API for the eShop. The wood client certificate is need to access this server.

When the eShop is opened, it visits `https://ninja.wup.shop.nintendo.net/ninja/wood_index.html?version=1.0.0&scene=detail&dst_title_id=<%016x>&src_title_id=<%016x>`. The server redirects the eShop to https://geisha-wup.cdn.nintendo.net/geisha/, which serves the real eShop website.

The geisha website accesses the ninja api through javascript. The following requests are known:

| Method | URL |
| --- | --- |
| GET | `/ninja/ws/country/<country>` |
| GET | `/ninja/ws/my/balance/current` |
| GET | `/ninja/ws/my/owned_titles` |
| GET | `/ninja/ws/my/shared_title_ids` |
| GET | `/ninja/ws/my/wishlist` |
| POST | `/ninja/ws/my/session/!open` |
| POST | `/ninja/debug/my/session/!open` |
| GET | `/ninja/debug/api/service_token` |
| GET | `/ninja/ws/<country>/title/public_status` |
| GET | `/ninja/ws/<country>/aoc/<item_code>/ns_uid` |
| GET | `/ninja/ws/my/votable_titles` |
| GET | `/ninja/ws/my/instant_votable_titles` |
| GET | `/ninja/ws/my/owned_coupons` |
| POST | `/ninja/ws/my/parental_control/!put` |
| POST | `/ninja/ws/my/session/!close` |

## Errors
On error, the server sends the following response:
```
<eshop>
  <error>
    <code>...</code>
    <message>...</message>
  </error>
</eshop>
```

Sometimes, the message tag is omitted.

### Known Errors
| Code | Message |
| --- | --- |
| 3001 | An error has occurred.<br>Please restart Nintendo eShop<br>and try again.<br><br>For help, please make a note<br>of the error code and visit<br>support.nintendo.com. |
| 3010 | The connection to the server has<br>timed out due to user inactivity.<br><br>Please restart Nintendo eShop<br>and try again. |
| 9404 | |
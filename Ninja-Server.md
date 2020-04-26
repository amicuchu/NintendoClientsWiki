## [[Server List]] > Ninja Server

The wood client certificate is need to access this server.

When the eShop is opened, it visits `https://ninja.wup.shop.nintendo.net/ninja/wood_index.html?version=1.0.0&scene=detail&dst_title_id=<%016x>&src_title_id=<%016x>`. The server redirects the eShop to https://geisha.wup.shop.nintendo.net/geisha/, which serves the real eShop website.

On logout, a POST request is sent to https://ninja.wup.shop.nintendo.net/ninja/ws/my/session/!close.
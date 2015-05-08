## Laravelの初期設定
-「app/config/app.php」と「app/config/database.php」を編集するだけ
- sudo php artisan key:generate /* 出たキーをどこかに保存 */
- sudo vi app/config/app.php 

'''
timezoneを「UTC」から「Asia/Tokyo」に変更
localeを「en」から「ja」に変更
key 設定 /* 先ほど key:generateで出したキーを設定 */
'''

- sudo vi app/config/database.php

'''
hostとdatabaseとusernameとpasswordの変更
'''


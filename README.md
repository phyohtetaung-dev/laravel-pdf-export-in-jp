# Export PDF in JP Language
## Sample
![image](https://user-images.githubusercontent.com/42564050/153977123-b2e9511c-e2c7-4fc5-a0e6-ccf9e76278d0.png)

## Installation
```
composer install
npm install && npm run dev
```

## Config
1. move **vendor/phenx/php-font-lib** to under **vendor/dompdf/dompdf/lib**
2. download load_font.php in https://github.com/dompdf/utils and save under **vendor/dompdf/dompdf**
3. change file path in line 3 of load_font.php. If you follow the steps file path will be **"../../autoload.php"**
4. download font in https://moji.or.jp/ipafont/ipa00303/ **IPAゴシック(Ver.003.03)** and save it in somewhere to reuse
5. cd into **"vendor/dompdf/dompdf"** and execute ```php load_font.php ipag $path_to_font_directory/ipag.ttf```
6. if you see the following, you are good to go
```
Unable to find bold face file.
Unable to find italic face file.
Unable to find bold_italic face file.
Copying $path_to_font_directory/ ipag.ttf to $laravel_install_directory /vendor/dompdf/dompdf/lib/fonts/ipag.ttf...
Generating Adobe Font Metrics for $laravel_install_directory /vendor/dompdf/dompdf/lib/fonts/ipag...
```
7. create a new folder under laravel storage directory
8. copy all files under **"vendor/dompdf/dompdf/lib/fonts"** to newly created folder
9. add the following into your html file
```html
<style>
    body {
      font-family: ipag;
    }
</style>
```

## Package
https://packagist.org/packages/barryvdh/laravel-dompdf

## Reference
https://reffect.co.jp/laravel/laravel-dompdf70-japanese

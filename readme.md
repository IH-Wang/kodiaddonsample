# A KODI skin structure sample
這是一篇關於客製化開發 kodi skin addon 的~~踩雷~~筆記！一般在使用 kodi 時，通常是在 `settings->appearance` 那設定或下載 skin，下載好後它會在 kodi 的 addons 目錄裡，設定過的全部 skin 設定檔會在 userdata 目錄裡的 addon_data 裡。


## **各環境路徑。(userdata 使用，非 Systemdata)**
| **Operative system** | **File path**                                             |
| -------------------- | --------------------------------------------------------- |
| Linux                | ~/.kodi/                                                  |
| Mac                  | /Users/<your_user_name>/Library/Application Support/Kodi/ |
| Windows              | Start - type %APPDATA%\kodi\ - press <Enter>              |


如果我們要手動設定 skin，則是到 userdata 這份檔案 guisettings.xml，編輯 `<skin>你的 skin name</skin>`，這樣啟動 kodi 時，會載入你的 skin addon。


    <lookandfeel>
            <enablerssfeeds default="true">true</enablerssfeeds>
            <font default="true">Default</font>
            <rssedit default="true"></rssedit>
            <skin>skin.kodisample</skin>
            <skincolors default="true">SKINDEFAULT</skincolors>
            <skintheme default="true">SKINDEFAULT</skintheme>
            <skinzoom default="true">0</skinzoom>
            <soundskin default="true">SKINDEFAULT</soundskin>
            <startupwindow default="true">10000</startupwindow>
            <stereostrength default="true">5</stereostrength>
        </lookandfeel>

關於 userdata 部分想了解更多，可參考[官網說明](http://kodi.wiki/view/Userdata)。




## **Skin structure**
- **skin.kodisample/1080i** - 這是設定各組件 skin 檔的目錄，而 Kodi 可以依照螢幕解析度作分辨，運行在不同的解析度上，所以你也可以建立 NTSC、720p、1080i 等不同解析度的目錄作區分。
- **skin.kodisample/backgrounds** - 在 skin 裡使用的背景圖片。(optional folder)
- **skin.kodisample/colors** - 在目錄建一個 defaults.xml 定義 skin 裡會使用到的顏色。(optional folder)
- **skin.kodisample/extras** - 包含額外的圖片或檔案。(optional folder)
- **skin.kodisample/fonts** - 字型檔存放目錄。
- **skin.kodisample/language** - 多國語言目錄字串定義，string.po 優先讀取，string.xml 其次。
- **skin.kodisample/media** - 多媒體檔案存放目錄。
- **skin.kodisample/addon.xml** - skin.kodisample addon 的描述定義檔。
- **skin.kodisample/changelog.txt** - skin.kodisample addon 版本更新記錄。
- **skin.kodisample/fanart.jpg** - a 1280x720 or 1920x1080 jpeg fanart image for your skin。
- **skin.kodisample/icon.png** - skin icon。
- **skin.kodisample/LICENSE.txt** - license 文件。




## **自定義 skin 描述檔（addon.xml）**
    <?xml version="1.0" encoding="UTF-8"?>
    <addon id="skin.kodisample" version="1.0.0" name="KODI Sample" provider-name="I-Heng Wang">
            <requires>
                    <import addon="xbmc.gui" version="4.0.0"/>
            </requires>
            <extension  point="xbmc.gui.skin" effectslowdown="1.00" debugging="false">
              <res width="1920" height="1080" aspect="16:9" default="true" folder="1080i" />
            </extenion>
            <extension point="xbmc.addon.metadata">
                    <platform>all</platform>
                    <summary>Enjoy the multimedia on your platform!</summary>
                    <source>https://github.com/IH-Wang/skin.kodisample</source>
            </extension>
    </addon>

詳細說明可參考[官網](http://kodi.wiki/view/Addon.xml)。




## **Skin 目錄基本檔案（1080i）**
- **defaults.xml** - 設定預設組件樣式
- **DialogBusy.xml** - (Fill viewport always for solving rendering passes)
- **DialogExtendedProgressBar.xml** - (Fill viewport always for solving rendering passes)
- **DialogKaiToast.xml** - toast 提示訊息 (Fill viewport always for solving rendering passes)
- **DialogMuteBug.xml** - (Fill viewport always for solving rendering passes)
- **DialogSeekBar.xml** - (Fill viewport always for solving rendering passes)
- **DialogVolumeBar.xml** - (Fill viewport always for solving rendering passes)
- **Font.xml** - 字型設定
- **Home.xml** - 首頁樣式設定
- **includes.xml** - 其他組件 xml 檔，通用常數及變數、組件設定
- **Pointer.xml** - 游標樣式設定 (Fill viewport always for solving rendering passes)
- **Startup.xml** - kodi 啟動時的 skin 檔
- **VideoFullScreen.xml** - 啟動時的 splash 畫面設定

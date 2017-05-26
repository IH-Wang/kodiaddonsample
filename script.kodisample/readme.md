# A KODI script structure sample
script 這類 addon 則是在 skin 或 service 的 addon.xml 裡的 `<requires></requires>` 有去 import 才會載入。
詳細可以參考[官網](http://kodi.wiki/view/Script_sources)

## **自定義 skin 描述檔（addon.xml）**
    <?xml version="1.0" encoding="UTF-8"?>
    <addon id="script.kodisample" version="1.0.0" name="Example script" provider-name="I-Heng Wang">
            <requires>
                    <import addon="xbmc.python" version="2.1.0"/>
            </requires>
            <extension point="xbmc.python.script" library="default.py" />
            <extension point="xbmc.addon.metadata">
                    <platform>all</platform>
                    <summary></summary>
            </extension>
    </addon>

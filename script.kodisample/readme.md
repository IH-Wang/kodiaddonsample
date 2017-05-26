# A KODI script structure sample
當 Kodi 啟動時， Service addons 會自動啟動。

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

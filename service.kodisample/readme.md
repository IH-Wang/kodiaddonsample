# A KODI service structure sample
當 Kodi 啟動時， Service addons 會自動啟動。

## **自定義 skin 描述檔（addon.xml）**
    <?xml version="1.0" encoding="UTF-8"?>
    <addon id="service.kodisample" version="1.0.0" name="Example service" provider-name="I-Heng Wang">
            <requires>
                    <import addon="xbmc.python" version="2.1.0"/>
            </requires>
            <extension point="xbmc.service" library="default.py" start="login" />
            <extension point="xbmc.addon.metadata">
                    <platform>all</platform>
                    <summary></summary>
            </extension>
    </addon>

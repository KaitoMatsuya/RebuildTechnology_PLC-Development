# RebuildTechnology_PLC-Development

About SLMP Ethernet Protocol(3E Frame)↓
1. https://qiita.com/BerandaMegane/items/b9cee359e8da90d4ce8e
2. https://qiita.com/hidehito108/items/e8eca75a46ee7d59feed
3. https://qiita.com/inari1047/items/f01f632989d5f5c51a11

Planned communication specifications:
Upon detecting an anomaly: Send 0x01 to PLC register D1 (rotating signal light activates).
Upon returning to normal: Send 0x01 to PLC register D2 (rotating signal light stops).

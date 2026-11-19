# 讀音規則檔（字體 12.005）

這四個檔和 Release `2026-11-15` 裡 PPT、Word zip 的 `GoodTeacher/` 資料夾逐檔相同，也是三個字體（WenKai、KaiPinyin、Zhuyin）Version 12.005 的規則來源。

- `rules.csv`：改讀音的規則（群組、動作、字、讀音編號、前文、後文、讀音提示；UTF-8 BOM、CRLF）。同一個字依檔案順序，第一條符合的就用。
- `readings.txt`：每個字的讀音清單，第一個是預設讀音。
- `classes.txt`：規則裡 `@GT_xxx` 的字類別。
- `variants.txt`：每個字有幾個字形變體（給 PPT、Word 外掛用）。

規則的正本維護在作者的 game-kit（私有）；字體更新時這裡會一起更新。

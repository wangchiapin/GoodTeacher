# GoodTeacher 拼音字體

> 台灣讀音拼音字體（文楷、正楷拼音、注音）與 PowerPoint、Word 外掛程式的發佈位置

- **網址：** https://wangchiapin.github.io/cadadiaunosminutos-share-zone/（下載入口）
- **Firebase 專案：** 不使用 Firebase
- **登入方式：** —
- **狀態：** 使用中
- **備註：** 檔案發佈在本 repo 的 **Releases**，入口網站與安裝說明 PDF 都從這裡下載。

## 文件
- `docs/遊戲讀音對照.md`（2026-10-25）：把 Ben 的遊戲與小工具裡「台灣讀音修正表」的 749 個詞，逐詞對照字體規則（Release 2026-10-13 的 `readings.txt` v10 ＋ `rules.csv`）。結果：完全一樣 669 筆、不一樣 93 筆（只有輕聲不同 51、念法真的不同 42）。限制：每個詞單獨檢查、沒放進整句，靠前後文的字要用字體實際打一次確認。

## 讀音規則怎麼更新（流程）
讀音規則（`rules.csv`、`readings.txt`、`classes.txt`）的**工作用正本放在 game-kit 的 `bank/gt/`**，GoodTeacher 的字體和外掛是照它做出來的。
1. 先在 game-kit 的 `bank/gt/rules.csv` 改規則，再重新產生遊戲與小工具的讀音資料（做法見 game-kit 的 `bank/README.md`「讀音（台灣讀音）」）。
2. 要更新 GoodTeacher 字體時，拿 game-kit 的 `bank/gt/rules.csv`（和 readings.txt、classes.txt）當依據，重新做三個字體，再把這三個檔放進 PPT／Word 兩個 zip 的 `GoodTeacher/` 資料夾。
3. 字體做好、Release 換好之後，字體、外掛與 game-kit 的規則檔就又一樣了。
- **第 1 步到第 3 步完成之前，兩邊會暫時不同**：遊戲與小工具已經照新規則，字體還是舊的。每次改規則都要記得做第 2、3 步。
- 最後一次確認兩邊一樣：Release 2026-11-15（字體 Version 12.001）的 PPT、Word zip 裡的三個資料檔，與 game-kit `bank/gt/` 逐檔比對相同。
- 規則寫法：同一格放多個字＝其中任何一個都可以（例如 `戰战`）；用 `|` 隔開＝連續的字。這在字體、PPT 巨集、遊戲三邊的比對方式一樣。規則是同一組裡第一條符合的就用，「不改」會停在原本讀音。

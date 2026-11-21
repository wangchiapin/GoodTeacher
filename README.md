# GoodTeacher 拼音字體

> 台灣讀音拼音字體（文楷、正楷拼音、注音）與 PowerPoint、Word 外掛程式的發佈位置

- **網址：** https://wangchiapin.github.io/cadadiaunosminutos-share-zone/（下載入口）
- **Firebase 專案：** 不使用 Firebase
- **登入方式：** —
- **狀態：** 使用中
- **備註：** 檔案發佈在本 repo 的 **Releases**，入口網站與安裝說明 PDF 都從這裡下載。

## 文件
- `docs/遊戲讀音對照.md`（2026-10-25）：把 Ben 的遊戲與小工具裡「台灣讀音修正表」的 749 個詞，逐詞對照字體規則（Release 2026-10-13 的 `readings.txt` v10 ＋ `rules.csv`）。結果：完全一樣 669 筆、不一樣 93 筆（只有輕聲不同 51、念法真的不同 42）。限制：每個詞單獨檢查、沒放進整句，靠前後文的字要用字體實際打一次確認。

## PowerPoint 外掛：「我的規則」功能（2026-11-21，測試中，還沒放上 Release）
PowerPoint 外掛新增「我的規則」：老師可以自己加讀音規則，不用等字體更新。Windows 的 PowerPoint 測試中；Mac 還沒測。Word 版之後再做。
- **工具列順序**：讀音標註 → 字型 → 我的規則 → 更新。
- **加入我的規則**：先選一個漢字，用「單字更換讀音」選好要的讀音，再按這顆。可以選「前面是某字時才用」「後面是某字時才用」「前後都符合才用」「每個都用」。有簡體／繁體另一種寫法的字（例如 著／着），會自動兩種都存。
- **管理我的規則**：列出自己加過的規則（越上面越優先），輸入數字刪除那一條（簡繁一起刪）、`a` 全部清除、`o` 開啟檔案（只有 Windows）。超過一頁時多一個 `n` 下一頁。
- **檢查更新**：看 GitHub Release 有沒有新版，只開下載頁，不會自動覆蓋檔案。
- **規則存放**：自己的規則存在 `myrules.csv`，位置在「文件\GoodTeacher我的規則」（Mac 是 GoodTeacher 資料夾旁的 `GoodTeacher-MyRules`）。更新外掛或內建規則不會蓋掉它。每次存檔前會先備份成 `myrules.bak`。
- **優先順序**：自己的規則先於內建的 `rules.csv`；自己的規則之間，條件越具體越優先（前後都有 > 只有一邊 > 不管前後），同樣具體就新的先。條件完全相同的規則會問是否取代。
- **舊投影片**要先按「還原所有讀音」，再按「校正讀音」，新規則才會套上去。
- **PPT zip 的 `GoodTeacher/` 資料夾現在有 6 個檔**：`rules.csv`、`readings.txt`、`classes.txt`、`variants.txt`、`version.txt`，另外新增 **`st.txt`**（簡體↔繁體對照表，只有「加入我的規則」用來找另一種寫法；沒有它仍可加規則，只是不會自動存簡繁兩種）。`st.txt` 不是從 game-kit 來的，改規則時不用動它；Word zip 目前不需要。
- 因為視窗限制，簡體字如果在 Windows 的對話視窗裡顯示不出來，會改寫成「著（簡）」這種形式。

## 讀音規則怎麼更新（流程）
讀音規則（`rules.csv`、`readings.txt`、`classes.txt`）的**工作用正本放在 game-kit 的 `bank/gt/`**，GoodTeacher 的字體和外掛是照它做出來的。
1. 先在 game-kit 的 `bank/gt/rules.csv` 改規則，再重新產生遊戲與小工具的讀音資料（做法見 game-kit 的 `bank/README.md`「讀音（台灣讀音）」）。
2. 要更新 GoodTeacher 字體時，拿 game-kit 的 `bank/gt/rules.csv`（和 readings.txt、classes.txt）當依據，重新做三個字體，再把這三個檔放進 PPT／Word 兩個 zip 的 `GoodTeacher/` 資料夾（PPT zip 的 `st.txt` 不用換）。
3. 字體做好、Release 換好之後，字體、外掛與 game-kit 的規則檔就又一樣了。
- **第 1 步到第 3 步完成之前，兩邊會暫時不同**：遊戲與小工具已經照新規則，字體還是舊的。每次改規則都要記得做第 2、3 步。
- 最後一次確認兩邊一樣：Release 2026-11-15（2026-11-18 已換成字體 Version 12.004 的檔案，zip 的校驗碼已和本機版逐一核對相同）。PPT、Word zip 裡的 rules.csv、readings.txt、classes.txt 與 game-kit `bank/gt/` 逐檔相同，三個字體也已照同一份 rules.csv 重建。
- 規則寫法：同一格放多個字＝其中任何一個都可以（例如 `戰战`）；用 `|` 隔開＝連續的字。這在字體、PPT 巨集、遊戲三邊的比對方式一樣。規則是同一組裡第一條符合的就用，「不改」會停在原本讀音。

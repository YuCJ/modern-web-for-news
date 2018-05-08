## 互動網頁製作軟體教學

## Github 和 Sourcetree

### Git 是什麼？

- 就是一套管理專案「版本」的工具：
  - 個人的版本控制
  - 團隊的版本控制
  - 專案的分支的版本控制

延伸閱讀： [猴子也能懂的 Git 入門](https://backlog.com/git-tutorial/tw/intro/intro1_1.html)

- 課程只需要瞭解最單純的情況：
  - 程式碼只作單線分支
  - 三個記錄狀態：雲端存一份版本記錄，你的電腦存一份版本記錄，還有你修改完但還沒存進版本記錄的檔案

### Github 和 Sourcetree 介面簡介

### 操作步驟提示

![HTML](assets/01-web-fundation-html.png)

**怎麼下載範例程式碼？**（Github + Sourcetree）

1. 註冊 Github 帳號和安裝 Sourcetree 軟體
2. 到 Github 網站上 [我們的專案範例程式碼](https://github.com/YuCJ/fullpage)  頁面 `fork`  程式碼到你自己的帳號
3. 到你自己的帳號裡找存在雲端的程式碼網址，透過 Sourcetree 軟體把程式碼 `clone` 下來你的電腦
4. 可以進行開發了～

**開發中要怎麼儲存新的版本記錄？**（Sourcetree）

1. 在 `[WorkSpace] -> [File Status]` 可以看到你現在有什麼檔案是修改過還沒有存到版本記錄
2. 把要存到版本紀錄的檔案通通打勾
3. 按左上角的 `commit +` ，就新增一個版本存檔了！（可以在 `[WorkSpace] -> [History]` 看到結果）

**要怎麼復原到之前的版本？**（Sourcetree）

1. 在 `[WorkSpace] -> [History]` 找到你要復原到的版本紀錄點
2. 對他按右鍵 -> [Reset master to this commit]
3. 問你要選什麼復原模式 -> 選 [Hard - discard all working copy changes] ，也就是會放棄記錄點之後的所有變更
4. 會跳出警告說「確定要放棄全部變更」嗎？選 [OK]
5. 復原完成

**要怎麼把做好的修改發佈到 Github 上面？**（Sourcetree）

1. 點上方工具列的 `Push ↑`
2. [Push to repository] 選 `origin` （後面網址就是你的專案在 Github 上的位置）
3. [Branches to push] ，把 local brach 和 remote branch 都選 `master` 並打勾
4. 點OK，可能會需要登入 Github 認證你有權限可以上傳到該專案
5. 上傳完成！

註：如果你有修改過過去的紀錄（例如曾經 reset 到先前的版本），在 `Push` 的對話視窗要把 [Force Push] 打勾才可以。如果對話視窗沒有出現 [Force Push]，請到工作列 [Sourcetree] -> [Preference] -> [Advanced] 把 [Allow Force Push] 打勾。

**怎麼公開網頁？**（Github）

1. 在你把範例程式碼 `fork` 到你自己的 Github Repositories 後，就可以到你的 Github 該 repo 頁面
2. 在專案頁面選 [Settings]
3. 滑到 [GitHub Pages] -> [Source] 選 master branch -> save
4. 上面就會出現你的專案發佈網址了！
5. 這個只要設定一次，以後你只要推新的程式碼版本到 `origin/master` branch，Github 就會自動幫你更新網頁



## VScode

- 介面簡介
- 開啟工作區
- 安裝plugin
- live server 使用
- 
# GitHub Fork 與上游貢獻計畫

## 目的

建立個人的公開 GitHub fork，發布可公開的自訂桌布組，並向原作者詢問
是否接受 AI 生成桌布貢獻。

這份文件只記錄後續操作計畫。目前尚未建立 fork、尚未安裝 GitHub CLI，
也尚未推送任何內容。

## 目前狀態

- 原作者 repo：`adi1090x/dynamic-wallpaper`
- 目前 `origin`：`https://github.com/adi1090x/dynamic-wallpaper.git`
- 上游 `master` commit：`65d515d`
- 本機 `master` 比上游多 2 個 commit：
  - `2ebf715 Add neon-dystopia wallpaper set`
  - `2823bdb 新增京都與宇治的AI生成壁紙集，更新README文件以包含新樣式與參考資料`
- 尚未 commit 的本機內容：
  - `images/alien-horror/`
  - 主 `README.md` 中的 `alien-horror` 說明
- 尚未安裝 `gh`
- 尚未登入 GitHub CLI
- 尚未建立個人 fork

## 公開範圍

可以推送到公開 fork：

- `images/neon-dystopia/`
- `images/kyoto/`
- `images/uji/`
- 上述桌布所需的 `README.md` 更新

不得推送到公開 fork：

- `images/alien-horror/`
- 主 `README.md` 中的 `alien-horror` 說明
- `AGENTS.md`
- 任何只供本機使用的分支

`alien-horror` 必須保持本機私有。禁止使用以下指令：

```bash
git push --all
git push --mirror
```

## 執行計畫

### 1. 保存本機完整狀態

先將目前包含 `alien-horror` 的完整工作狀態保存到只存在本機的分支，
並保留目前已有 2 個 commit 的歷史。

建議本機分支名稱：

- `local/alien-horror`
- `local/original-history`

這些分支不得推送到公開 fork。

### 2. 安裝與登入 GitHub CLI

系統為 Linux Mint 22.3。使用 GitHub CLI 官方 apt repository 安裝最新版
`gh`，不要直接使用 Linux Mint repository 中較舊的版本。

安裝後使用瀏覽器登入：

```bash
gh auth login --web --git-protocol https
```

登入後確認：

```bash
gh auth status
gh api user --jq '.login'
gh api user/emails
```

公開 commit 使用 GitHub noreply email，避免目前的 Gmail 出現在公開 Git
歷史。

### 3. 建立個人 Fork 與 Remote

建立 fork：

```bash
gh repo fork adi1090x/dynamic-wallpaper --clone=false
```

Remote 命名原則：

- `upstream` 指向 `https://github.com/adi1090x/dynamic-wallpaper.git`
- `origin` 指向個人 GitHub fork

完成後確認：

```bash
git remote -v
```

### 4. 建立乾淨的公開歷史

從 `upstream/master` 建立新的乾淨公開分支，不直接推送目前的本機
`master`，避免公開 `AGENTS.md`、`alien-horror` 或 Gmail commit metadata。

公開歷史重建為三個獨立 commit：

1. `Add neon-dystopia wallpaper set`
2. `Add Kyoto wallpaper set`
3. `Add Uji wallpaper set`

每個 commit 僅包含該桌布組及必要的 `README.md` 更新。

確認公開分支不包含私有內容後，僅推送指定分支：

```bash
git push -u origin master
```

### 5. 向原作者開一次 Issue

原作者 repo 最後一次 push 與合併 PR 是 2023-08-22，且 README 說明大型
桌布組通常不放進主 repo。因此先開 Issue 詢問，不直接建立 Pull Request。

建議 Issue title：

```text
Question: preferred way to contribute AI-generated wallpaper sets
```

Issue 內容應包含：

- 三組可公開桌布：`neon-dystopia`、`kyoto`、`uji`
- 每組檔案數量與約略大小
- 個人 fork 連結與預覽
- 說明桌布為 AI 生成
- 詢問維護者偏好：
  - 每組獨立 Pull Request
  - 放到外部 wallpaper download repo
  - 不接受大型或 AI 生成素材
- 明確說明尚未建立 Pull Request，等待維護者指示

若原作者沒有回覆，停止於維護個人公開 fork，不重複催促。

若原作者接受，再從 `upstream/master` 為每組桌布建立獨立 PR 分支。

## 驗證清單

建立公開 fork 與推送前，必須確認：

- `origin` 指向個人 fork
- `upstream` 指向原作者 repo
- 公開分支只包含 `neon-dystopia`、`kyoto`、`uji` 與必要文件
- 公開分支不包含 `AGENTS.md`
- 公開分支不包含 `alien-horror`
- 公開 commit 使用 GitHub noreply email
- 沒有使用 `git push --all` 或 `git push --mirror`

執行靜態驗證：

```bash
bash -n dwall.sh install.sh test.sh uninstall.sh
./test.sh -h
git diff --check
```

不要執行會直接切換桌布的：

```bash
./test.sh -s <style>
```

## 參考文件

- [GitHub CLI Linux 安裝說明](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)
- [GitHub CLI 登入說明](https://cli.github.com/manual/gh_auth_login)
- [設定 Fork Remote](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-repository-for-a-fork)
- [從 Fork 建立 Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)

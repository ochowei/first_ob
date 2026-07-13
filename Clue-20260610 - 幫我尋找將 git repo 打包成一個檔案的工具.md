---
created: 2026-06-10
kind: clue
source_type: conversation
needs_browsing: false
reviewed: false
last_reviewed:
---

# 幫我尋找將 git repo 打包成一個檔案的工具

## Raw Capture

將 Git Repo（儲存庫）打包成單一檔案的工具，會因您的打包目的而有不同的選擇。以下為您整理了最常見的幾種類型與對應工具：1. 給 AI (如 ChatGPT, Claude, Gemini) 閱讀專用如果您是為了將整個專案的程式碼餵給 AI，以便進行程式碼分析或重構，建議使用專門的 Repo to Text 工具。它們會過濾掉不必要的 Git 歷史紀錄，將程式碼整理成適合 AI 閱讀的單一純文字或 Markdown 檔案。

- [Repopack](https://github.com/r-dh/repopack) (原 Repomix)：強大的開源命令列工具，可將整個 repo 打包成單一 AI 友善檔案 Repopack。
- [GitIngest](https://www.youtube.com/watch?v=bKE78yBZ054)：只需貼上 GitHub 網址或輸入本機目錄，即可線上將 Repo 轉成結構化的 Markdown 檔 GitIngest。
- [Repo2Txt](https://repo2txt.com/)：提供網頁版與 CLI 工具，將程式碼庫轉換為單一格式化文字檔 Repo2Txt。
- [repo-to-text](https://github.com/kirill-markin/repo-to-text)：熱門的 Python 套件與 CLI 工具，能自動合併並產生專案結構與內容 repo-to-text。

## Notes

## Possible Follow-up

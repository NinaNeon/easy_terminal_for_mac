
nina@nina-X550VX:~$ sudo ddcutil setvcp 10 30

亮30


nina@nina-X550VX:~$ sudo ddcutil setvcp 10 10


亮10

# 保持你的 Mac 醒著，不睡覺
```bash
caffeinate -i -t 86400
```
# 開webui
```bash
cd stable-diffusion-webui
conda activate sdwebui
./webui.sh
```

亂裝東西
nina@ninadeMacBook-Air ~ % pyenv install 3.10.6
pyenv global 3.10.6

python-build: use openssl@3 from homebrew
python-build: use readline from homebrew
Downloading Python-3.10.6.tar.xz...
-> https://www.python.org/ftp/python/3.10.6/Python-3.10.6.tar.xz
Installing Python-3.10.6...
python-build: use readline from homebrew
python-build: use zlib from xcode sdk
Installed Python-3.10.6 to /Users/nina/.pyenv/versions/3.10.6
nina@ninadeMacBook-Air ~ % python --version

Python 3.10.6
nina@ninadeMacBook-Air ~ % 



# easy_terminal_for_mac
在 MacBook (M1) 上用 Terminal 安全 Eject 隨身碟的方法：

```bash
diskutil list
```
<img width="893" alt="截圖 2025-04-28 中午12 03 53" src="https://github.com/user-attachments/assets/834f70a9-0d79-434c-b5eb-474bb5fd45a5" />

```bash
diskutil eject disk8
```
可以試 diskutil unmountDisk force disk2 強制卸載（但通常不用）


# 超完整流程：用 SSH 把 3D-Demo 專案推上 GitHub（macOS）

⸻

📌 一次搞定的情境：
	•	✅ 你本地資料夾叫 3D-Demo
	•	✅ GitHub 上已建立 repo 名為 3D-Demo
	•	✅ 你要用 SSH（不是 HTTPS）
	•	✅ 你要會「第一次設定」+「後續每次更新」
	•	✅ 你不想看到漏半套的教學

⸻

🔧 Step 1：產生 SSH 金鑰（只做一次）
```bash
ssh-keygen -t ed25519 -C caijingnina@gmail.com
```
按三次 Enter（一路預設）

然後輸入：
```bash
cat ~/.ssh/id_ed25519.pub
```

```bash
nina@ninadeMacBook-Air 3d-demo2 % ssh-keygen -t ed25519 -C caijingnina@gmail.com 
Generating public/private ed25519 key pair.
Enter file in which to save the key (/Users/nina/.ssh/id_ed25519): 
/Users/nina/.ssh/id_ed25519 already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/nina/.ssh/id_ed25519
Your public key has been saved in /Users/nina/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:MFoD3mvNrwh3+P83D1KG2jvXrqhdbrfrYctW77jkuec caijingnina@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
|    .            |
|   . o           |
|    . *          |
|     o B     .   |
|    . o S   . o  |
|     . . . o o  .|
|    . o . o o ++o|
|     o + . ..OB=B|
|      . o.oo==@^E|
+----[SHA256]-----+
nina@ninadeMacBook-Air 3d-demo2 % cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIPv7uGpzcdGsWB5nUxyxarezMaxoQ0fmiawMOXvzJ6wY caijingnina@gmail.com

nina@ninadeMacBook-Air 3d-demo2 % git remote set-url origin git@github.com:NinaNeon/3d-demo-2.git
nina@ninadeMacBook-Air 3d-demo2 % git push -u origin main --force
Enumerating objects: 172, done.
Counting objects: 100% (172/172), done.
Delta compression using up to 8 threads
Compressing objects: 100% (172/172), done.
Writing objects: 100% (172/172), 4.66 MiB | 2.68 MiB/s, done.
Total 172 (delta 108), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (108/108), done.
To github.com:NinaNeon/3d-demo-2.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
nina@ninadeMacBook-Air 3d-demo2 % git remote -v
origin	git@github.com:NinaNeon/3d-demo-2.git (fetch)
origin	git@github.com:NinaNeon/3d-demo-2.git (push)
nina@ninadeMacBook-Air 3d-demo2 % git push -u origin main --force

branch 'main' set up to track 'origin/main'.
Everything up-to-date
nina@ninadeMacBook-Air 3d-demo2 % git add .
git commit -m "Update main.js and other files"
git push origin main
[main e6f60dd] Update main.js and other files
 Committer: nina <nina@ninadeMacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+), 1 deletion(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 301 bytes | 301.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:NinaNeon/3d-demo-2.git
   8f25eae..e6f60dd  main -> main
nina@ninadeMacBook-Air 3d-demo2 % cd /Users/nina/Downloads/HW3/3d-demo
nina@ninadeMacBook-Air 3d-demo % git checkout -- .
nina@ninadeMacBook-Air 3d-demo % git status         # 確認有哪些變更
git add .
git commit -m "Restore original version"
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
nina@ninadeMacBook-Air 3d-demo % git remote set-url origin https://github.com/NinaNeon/3d-demo.git
git push origin main --force
remote: Permission to NinaNeon/3d-demo.git denied to NinaNeon.
fatal: unable to access 'https://github.com/NinaNeon/3d-demo.git/': The requested URL returned error: 403
nina@ninadeMacBook-Air 3d-demo % cd /Users/nina/Downloads/HW3/3d-demo

git remote set-url origin git@github.com:NinaNeon/3d-demo.git

git remote -v
origin	git@github.com:NinaNeon/3d-demo.git (fetch)
origin	git@github.com:NinaNeon/3d-demo.git (push)
nina@ninadeMacBook-Air 3d-demo % git push origin main --force
Enumerating objects: 163, done.
Counting objects: 100% (163/163), done.
Delta compression using up to 8 threads
Compressing objects: 100% (163/163), done.
Writing objects: 100% (163/163), 888.43 KiB | 3.90 MiB/s, done.
Total 163 (delta 102), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (102/102), done.
To github.com:NinaNeon/3d-demo.git
 + 8f25eae...c85fd59 main -> main (forced update)
nina@ninadeMacBook-Air 3d-demo % cd /Users/nina/Downloads/HW3/3d-demo2
nina@ninadeMacBook-Air 3d-demo2 % git remote set-url origin git@github.com:NinaNeon/3d-demo-2.git
nina@ninadeMacBook-Air 3d-demo2 % git push -u origin main --force
branch 'main' set up to track 'origin/main'.
Everything up-to-date
nina@ninadeMacBook-Air 3d-demo2 % git remote -v
origin	git@github.com:NinaNeon/3d-demo-2.git (fetch)
origin	git@github.com:NinaNeon/3d-demo-2.git (push)
nina@ninadeMacBook-Air 3d-demo2 % git add main.js
git commit -m "Force update: tweak to main.js"
git push origin main
[main 155393f] Force update: tweak to main.js
 Committer: nina <nina@ninadeMacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 323 bytes | 323.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:NinaNeon/3d-demo-2.git
   e6f60dd..155393f  main -> main
nina@ninadeMacBook-Air 3d-demo2 % git add main.js
git commit -m "Force update: tweak to main.js"
git push origin main
[main 0dc628f] Force update: tweak to main.js
 Committer: nina <nina@ninadeMacBook-Air.local>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly:

    git config --global user.name "Your Name"
    git config --global user.email you@example.com

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+), 1 deletion(-)
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 309 bytes | 309.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:NinaNeon/3d-demo-2.git
   155393f..0dc628f  main -> main

```




把整串複製起來（從 ssh-ed25519 開頭）

⸻

🌐 Step 2：到 GitHub 貼上 SSH 金鑰
	•	網址：https://github.com/settings/keys
	•	點 New SSH key
	•	Title：MacBook
	•	Key type：Authentication Key
	•	Key：貼剛剛那串
	•	按 Add SSH Key

⸻

🧪 Step 3：測試連線是否成功
```bash
ssh -T git@github.com
```

若看到：

Hi NinaNeon! You've successfully authenticated...

✅ SSH OK！

⸻

🚀 Step 4：初始化並推送本地 repo
```bash

cd ~/Desktop/3D-Demo       # 進入資料夾（不用空格）
git init                   # 初始化 git
git add .                  # 加入全部檔案
git commit -m "Initial commit"

git remote add origin git@github.com:NinaNeon/3D-Demo.git
git branch -M main
git push -u origin main
```

⸻

🔁 Step 5：以後每次更新只做這 3 行
```bash
cd ~/Desktop/3D-Demo
git add .
git commit -m "更新說明"
git push
```

⸻

✅ 檢查遠端是否正確（一定要是 SSH）
```bash
git remote -v
```
應該會顯示：

origin  git@github.com:NinaNeon/3D-Demo.git (fetch)
origin  git@github.com:NinaNeon/3D-Demo.git (push)

這個問題很關鍵，你問得完全正確。我幫你分成兩種情況講清楚：

---

## ✅ 情況 1：你**沒動過本地的檔案** → 可以直接 `git pull`，再繼續推

如果你只是：

* 在 GitHub 上小改了幾個檔案
* 本地還沒做任何更動

那你本地只要這樣做：

```bash
git pull origin main  # 把 GitHub 改動拉下來
# 然後你再做新的修改
git add .
git commit -m "新修改"
git push
```

這是最順的情況，**本地就會跟 GitHub 同步了，之後都可以繼續推送。**

---

## ⚠️ 情況 2：你**本地有改，但還沒 push，GitHub 上也有改**

這會產生「**分支衝突**」，你不能直接推上去。

你會看到錯誤像這樣：

```
! [rejected]        main -> main (fetch first)
error: failed to push some refs to '...'
hint: Updates were rejected because the remote contains work that you do
```

### ➤ 解法（有兩種）：

#### ✅ A. 把 GitHub 改動先拉下來，手動合併（推薦）

```bash
git pull origin main  # 會出現 conflict，就手動解
# 解完 conflict 後：
git add .
git commit -m "Resolve conflict"
git push
```

這是最安全也最常用的方式。

---

#### ❌ B. 強制推送（不推薦，會**覆蓋 GitHub 上的內容**）

```bash
git push --force
```

只有在你非常確定 GitHub 上的東西不要保留時才用。

---

## 🔚 總結

| 你做的情況       | 是否可以直接 push | 建議做法                   |
| ----------- | ----------- | ---------------------- |
| 只有 GitHub 改 | ❌（需先 pull）  | `git pull` 合併後再 push   |
| 只有本地改       | ✅           | 直接 push                |
| 兩邊都有改       | ❌           | 建議手動解 conflict，除非你想強制推 |

---

如果你現在不確定你本地和 GitHub 差在哪裡，我可以教你怎麼 `git fetch` 看差異，幫你搞清楚要不要 reset 或 merge。需要的話直接說。

push
git remote set-url origin git@github.com:NinaNeon/ODISE.git
git remote -v
git push -u origin HEAD




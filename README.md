# easy_terminal_for_mac
在 MacBook (M1) 上用 Terminal 安全 Eject 隨身碟的方法：

```bash
diskutil list
```
<img width="893" alt="截圖 2025-04-28 中午12 03 53" src="https://github.com/user-attachments/assets/834f70a9-0d79-434c-b5eb-474bb5fd45a5" />

```bash
diskutil eject disk2
```
可以試 diskutil unmountDisk force disk2 強制卸載（但通常不用）

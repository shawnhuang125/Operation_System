# Winodws基本指令
## 用戶管理
### 進入 Windows 安全模式：

- 在登入畫面，按住 Shift 鍵並點擊右下角的「重新啟動」。
- 系統將重新啟動並進入 Windows 恢復環境。
- 選擇「疑難排解」→「進階選項」→「啟動設定」，然後點擊「重新啟動」。
- 重新啟動後，選擇「安全模式」進入 Windows。
- 替換便利鍵 (Ease of Access) 啟動 PowerShell：

- 進入 Windows 恢復環境後，選擇「命令提示字元」。
- 然後在命令提示字元中，輸入以下指令來備份原有的「便利鍵」檔案，並將其替換為 cmd.exe：
```
copy C:\Windows\System32\utilman.exe C:\Windows\System32\utilman.exe.bak
copy C:\Windows\System32\cmd.exe C:\Windows\System32\utilman.exe
```
- 注意：這個步驟會暫時將「便利鍵」功能替換為命令提示字元。

### 重啟電腦並回到登入畫面：

- 在登入畫面中，按下螢幕右下角的「便利鍵」圖標，這時候應該會啟動命令提示字元而不是便利功能。
- 從命令提示字元啟動 PowerShell：

- 在命令提示字元中輸入以下命令以啟動 PowerShell：
```
powershell
```
### 查看用戶名稱
```
whoami
```
- ![image](https://github.com/user-attachments/assets/8083ab0a-4403-48ac-bede-0ef46db85537)
### 修改用戶密碼
```
net user user ""
```
- ![image](https://github.com/user-attachments/assets/7971ed0c-24a2-40fb-b47d-9138ef5b34c1)


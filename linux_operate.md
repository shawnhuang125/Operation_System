# Linux 基礎操作
## link
- [外部資源](https://linux.vbird.org/linux_basic_train/rockylinux9/unit01.php)
- [積點系統](https://irs.ctlin.tw/dashboard)

## AGENDA
### 文件操作：
- ls： 上市文件和目錄
- cd： 切換目錄
- cp：複製檔案或目錄
- mv：移動或重新命名文件
- rm：刪除檔案或目錄
- mkdir：建立目錄

### 權限管理：
- chmod：修改檔案權限
- chown：更改文件所有者
- sudo：臨時取得使用者超級權限

### 系統管理：
- ps：查看運行中的進程
- top或htop：即時監控系統資源
- kill： 終止進程
- df：查看磁碟空間使用情況
- du：查看目錄或檔案的磁碟佔用情況

### 網路管理：
- ifconfig或ip addr：查看網路介面資訊
  ```
  ifconfig
  ```
  - ![螢幕擷取畫面 2024-09-15 151359](https://github.com/user-attachments/assets/3cbce61d-8fdf-4c93-82e6-81423322683c)
  - 檢視網路端口的詳細訊息
  - ![螢幕擷取畫面 2024-09-15 152236](https://github.com/user-attachments/assets/a5d6d2de-41b6-407d-900b-b3102ca03861)
  - 查看所有的網路端口及其配置
  ```
  ifconfig -a
  ```
  - ![螢幕擷取畫面 2024-09-15 152702](https://github.com/user-attachments/assets/5b12adf9-e0b5-4749-9d5e-1273c00efc50)
- 查找包含192.168的本地IP
- ![螢幕擷取畫面 2024-09-15 155112](https://github.com/user-attachments/assets/daee0344-91f3-44f3-87dd-1424cd7b7df4)

- ping：測試網絡連接,與router傳送封包
  - 連不到
  ```
  ping 192.168.x.xxx
  ```
  - ![螢幕擷取畫面 2024-09-15 153009](https://github.com/user-attachments/assets/b8c46b87-1910-4315-977f-2c9e97af2354)
  - 連接成功,封包傳送與接收正常
  ```
  ping 192.168.x.xxx
  ```
  - ![螢幕擷取畫面 2024-09-15 152934](https://github.com/user-attachments/assets/40d9a229-683b-417b-a8f4-4a512561ece0)
- netstat或ss：查看網路連線狀態
  - 監聽TCP協議的連接端口
  ```
  netstat -at
  ```
  監聽UDP協議的連接端口
  ```
  netstat -au
  ```
  - ![螢幕擷取畫面 2024-09-15 154900](https://github.com/user-attachments/assets/61f1a340-1467-4e9e-b83a-06682b8f6681)
  - 使用ss工具檢查系統網路連接
  ```
  ss -tunip
  ```
  - ![螢幕擷取畫面 2024-09-15 160245](https://github.com/user-attachments/assets/c5a250d1-00ed-43da-aeb3-57a6ffa104f3)
  - ss -tunip命令解析：
  ```
  -t：顯示TCP連線。
  -u：顯示UDP連接。
  -n：不解析主機名稱或服務名稱，顯示數字位址和連接埠。
  -i：顯示更多的網路狀態訊息，例如TCP指標。
  -p：顯示使用該連線的進程資訊。
  ```
### 服務管理：
- 重啟機器
  - 使用最高權限即時重啟：
  ```
  sudo reboot
  ```
  - 使用最高權限並使用systemtl工具來重啟
  ```
  sudo systemctl reboot
  ```
  - 使用最高權限定時重啟（在 10 分鐘後重啟）：
  ```
  sudo shutdown -r +10
  ```
  - 使用最高權限重啟在指定時間（例如：在晚上 11 點重啟）：
  ```
  sudo shutdown -r 23:00
  ```
- 關閉機器
  - 使用最高權限立即關機：
  ```
  sudo shutdown now
  ```
  - 使用最高權限立即關機：
  ```
  sudo poweroff
  ```
  - 使用最高權限立即停止cpu運行,但不關閉電源：
  ```
  sudo halt
  ```
  - 使用最高權限關機（進入運行級別 0）：
  ```
  sudo init 0
  ```
- 使用systemctl來管理服務
  ```
  sudo systemctl status [service]
  ```
  - 例如開啟ssh並檢查ssh狀態最後關閉,檢查狀態
  ```
  sudo systemctl start ssh
  ```
  ```
  sudo systemctl status ssh
  ```
  ```
  ssh systemctl stop ssh
  ```
### init是一個用來管理系統的程式
- 使用最高權限切換運行級別： 使用 init 或 telinit 命令來切換運行級別。例如，切換到運行級別 3（多用戶模式）：
  - 多用戶模式:關掉機器的圖形化介面,只使用tty1-6進行終端指令輸入,可開啟ssh服務進行遠程造訪。
  ```
  sudo init 3
  ```
  - 或
  ```
  sudo telinit 3
  ```
  - 如何關閉init 3?
  - 按ctrl+alt+f1-f6輸入指令
  ```
  sudo systemctl isolate graphical.target
  ```
  - 或
  ```
  sudo init 5
  ```
  - 或按ctrl+alt+f7
- 使用最高權限關機（運行級別 0）：
```
sudo init 0
```
- 使用最高權限重啟（運行級別 6）：
```
sudo init 6
```
### 命令行終端（TTY）模式
- TTY1-TTY6都是終端介面,可以一次開很多個使用
- TTY7是圖形化介面專用,可以用來切回圖形化介面模式

### 用戶管理：


> 應用場景
  系統管理員希望給予某個使用者臨時的管理權限，以便他們可以執行某些管理任務。
  提高伺服器的安全性,防止遭受惡意攻擊
  在企業中不同的部門會有不同的存取權限,可以使用此功能管理使用者訪問權限
  使用SSH連線伺服器時可以管理不同的使用者身分,有異常的可以直接刪除

- useradd和userdel：新增或刪除用戶
- passwd：修改用戶密碼
- usermod：修改使用者資訊


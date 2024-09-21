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
  - ![螢幕擷取畫面 2024-09-16 101230](https://github.com/user-attachments/assets/99b8a618-0abf-4658-a117-cd4eac3e91a3)
  - ![螢幕擷取畫面 2024-09-16 101015](https://github.com/user-attachments/assets/99e1a481-236a-435d-a066-23b606b11be3)


  - 使用最高權限並使用systemtl工具來重啟
  ```
  sudo systemctl reboot
  ```
  - ![螢幕擷取畫面 2024-09-16 101457](https://github.com/user-attachments/assets/f67cf5cf-bb55-430c-ae1d-f58dabb70361)
  - ![螢幕擷取畫面 2024-09-16 101015](https://github.com/user-attachments/assets/c81e7073-1538-4d6d-9bf9-71a10fb59ef4)


  - 使用最高權限定時重啟（在 10 分鐘後重啟）：
  ```
  sudo shutdown -r +10
  ```
  - ![螢幕擷取畫面 2024-09-16 101724](https://github.com/user-attachments/assets/ee9f5a53-98f3-4791-bbec-f97374b2398a)
  - ![螢幕擷取畫面 2024-09-16 101914](https://github.com/user-attachments/assets/4c65eb2e-5a8e-444d-91e0-27f1be590601)
  - ![螢幕擷取畫面 2024-09-16 101958](https://github.com/user-attachments/assets/5eb71bfc-e619-41df-b83b-d83a69fe3e18)

  - 使用最高權限重啟在指定時間（例如：在晚上 11 點重啟）：
  ```
  sudo shutdown -r 23:00
  ```
  - ![螢幕擷取畫面 2024-09-16 102151](https://github.com/user-attachments/assets/4f84ea4f-b933-4d98-b3ac-1da19dccf43d)
  - ![螢幕擷取畫面 2024-09-16 102151](https://github.com/user-attachments/assets/977a9a1c-3af7-4585-81c1-cccf0679d723)

- 關閉機器
  - 使用最高權限立即關機：
  ```
  sudo shutdown now
  ```
  - ![螢幕擷取畫面 2024-09-16 102354](https://github.com/user-attachments/assets/7159af13-68f7-4072-aa09-dd29f0f405d3)
  - ![螢幕擷取畫面 2024-09-16 102406](https://github.com/user-attachments/assets/36dd30ec-10a3-443a-86a9-b9c80e7ab094)

  - 使用最高權限立即關機：
  ```
  sudo poweroff
  ```
  - 使用最高權限立即停止cpu運行,但不關閉電源：
  ```
  sudo halt
  ```
  - ![螢幕擷取畫面 2024-09-16 104709](https://github.com/user-attachments/assets/7b06e54f-3783-4bb8-91b6-a0c1cf63eef7)
  - ![螢幕擷取畫面 2024-09-16 104724](https://github.com/user-attachments/assets/cfb48ebd-b56e-4c2b-b342-c1036374b126)

  - 使用最高權限關機（進入運行級別 0）：
  ```
  sudo init 0
  ```
  - ![螢幕擷取畫面 2024-09-16 104927](https://github.com/user-attachments/assets/184059c9-b200-4b19-9874-b777b425d32b)

- 使用systemctl來管理服務
  ```
  sudo systemctl status [service]
  ```
  - 例如開啟ssh並檢查ssh狀態最後關閉。
  ```
  sudo systemctl start ssh
  ```
  - ![螢幕擷取畫面 2024-09-16 110928](https://github.com/user-attachments/assets/fcab0342-6297-47f5-81f1-616c66941087)
  - 檢查ssh狀態

  ```
  sudo systemctl status ssh
  ```
  - ![螢幕擷取畫面 2024-09-16 110937](https://github.com/user-attachments/assets/0e9c9e22-5ae9-468a-a73a-224c15fcd13f)
  - 關閉ssh服務
  ```
  ssh systemctl stop ssh
  ```
  - ![螢幕擷取畫面 2024-09-16 111007](https://github.com/user-attachments/assets/e18d2050-ec53-48f9-a263-669e2bbcb464)

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
- ![螢幕擷取畫面 2024-09-16 104927](https://github.com/user-attachments/assets/969b3e63-21f5-4bda-b6b4-7c391fff0a6a)
- ![螢幕擷取畫面 2024-09-16 102406](https://github.com/user-attachments/assets/9843cada-efb0-402f-a266-41d550ac8ca2)

- 使用最高權限重啟（運行級別 6）：
```
sudo init 6
```
- ![螢幕擷取畫面 2024-09-16 112303](https://github.com/user-attachments/assets/456b6fca-5093-4c31-adf5-00bde9b1ec7f)
- ![螢幕擷取畫面 2024-09-16 112327](https://github.com/user-attachments/assets/85db3bab-35f2-4e9f-9d4c-cf909481e62c)
- ![螢幕擷取畫面 2024-09-16 101555](https://github.com/user-attachments/assets/31004e1e-36ed-4d32-bc82-69bb6f3c5d04)

### 命令行終端（TTY）模式
- TTY1-TTY6都是終端介面,可以一次開很多個使用
- TTY7是圖形化介面專用,可以用來切回圖形化介面模式
## 實戰演練
- 描述:root權限使用ssh連線至kali linux,並將kali linux關閉圖形介面
- **先查看機器本地端IP**
- ![螢幕擷取畫面 2024-09-16 112855](https://github.com/user-attachments/assets/b5ec86a5-ff25-4673-96aa-2b0c1f7faabf)
- **檢查SSH狀態並開啟服務**
- ![螢幕擷取畫面 2024-09-16 112937](https://github.com/user-attachments/assets/4ce431e0-7a9a-4600-af74-39eb179937fc)
- **切換至TTY3模式**
- ![螢幕擷取畫面 2024-09-16 113343](https://github.com/user-attachments/assets/04136954-8e77-4955-af59-ee1fb226a9b8)
- **開啟SSH服務並檢查SSH服務狀態**
- ![螢幕擷取畫面 2024-09-16 113633](https://github.com/user-attachments/assets/7b3e69ba-50d3-4235-b87b-0c147d2c68da)
- **查看機器本地端IP並使用CMD連線**
- ![螢幕擷取畫面 2024-09-16 113752](https://github.com/user-attachments/assets/81cfe090-f727-4633-9a05-d3d6fec028b2)
- **離開SSH連線**
![螢幕擷取畫面 2024-09-16 113813](https://github.com/user-attachments/assets/e69369d3-b8f0-4fc8-97ba-11a4dfe832b0)
- **重新開啟圖形介面請調至TTY7**
- 按: Ctrl + Alt + F7
- **或輸入以下**
```
sudo systemctl isolate graphical.target
```
- ![螢幕擷取畫面 2024-09-16 113509](https://github.com/user-attachments/assets/fc510ef1-6def-4473-bff8-6440ed43bf21)
- ![螢幕擷取畫面 2024-09-16 113509](https://github.com/user-attachments/assets/bdf5594c-c754-4387-a21f-0afa86834752)

### 用戶管理：
> 應用場景
  系統管理員希望給予某個使用者臨時的管理權限，以便他們可以執行某些管理任務。
  提高伺服器的安全性,防止遭受惡意攻擊
  在企業中不同的部門會有不同的存取權限,可以使用此功能管理使用者訪問權限
  使用SSH連線伺服器時可以管理不同的使用者身分,有異常的可以直接刪除

- **useradd和userdel：新增或刪除用戶**
```
sudo useradd [name]
```
- **這邊是使用"client"作為新增用戶名稱**
```
sudo useradd client
```
- ![螢幕擷取畫面 2024-09-18 162413](https://github.com/user-attachments/assets/856023dd-0466-4211-9a4a-059c250e9706)
- **輸入自訂義用戶密碼==>成功添加**
- ![螢幕擷取畫面 2024-09-18 162525](https://github.com/user-attachments/assets/83028843-ecbd-4342-8223-f728d28c5f66)
- 建立用戶資料夾
```
sudo mkdir /home/client
```
- ![螢幕擷取畫面 2024-09-18 163800](https://github.com/user-attachments/assets/ac82e3ad-82b4-46bc-bed2-b0fe77c198d1)
- 查看目錄是否建立成功
- **進入/home**
```
cd /home
```
- 列出位於此目錄下之所有目錄
```
ls
```
- ![螢幕擷取畫面 2024-09-18 163807](https://github.com/user-attachments/assets/96bb09b6-fb89-4d48-9487-3566fae3ca93)
- ![螢幕擷取畫面 2024-09-18 163807](https://github.com/user-attachments/assets/dfcd724b-ec85-4a49-8b7e-7b2b197a8214)
- **賦予"client"操作權限**
```
sudo chown cleint:client /home/client
```
- **查看權限資訊**
```
ls -ld /home/client
```
- ![螢幕擷取畫面 2024-09-18 164037](https://github.com/user-attachments/assets/54a3928f-83f8-4455-9d11-f30f124a3bf8)
- ![image](https://github.com/user-attachments/assets/a1af8de9-c00a-44d7-ad52-796eae2a8550)

- passwd：修改用戶密碼

- usermod：修改使用者資訊



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
## 實戰演練1
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
- ![螢幕擷取畫面 2024-09-16 113509](https://github.com/user-attachments/assets/fc510ef1-6def-4473-bff8-6440ed43bf21)
- **或輸入以下**
```
sudo systemctl isolate graphical.target
```
- ![螢幕擷取畫面 2024-09-16 113509](https://github.com/user-attachments/assets/fc510ef1-6def-4473-bff8-6440ed43bf21)

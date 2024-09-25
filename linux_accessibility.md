# 權限管理：
- chmod：修改檔案權限
  

- chown：更改文件所有者
  - **賦予"client"操作權限**
  ```
  sudo chown cleint:client /home/client
  ```
  - ![螢幕擷取畫面 2024-09-18 164037](https://github.com/user-attachments/assets/54a3928f-83f8-4455-9d11-f30f124a3bf8)
  - **查看權限資訊**
  ```
  ls -ld /home/client
  ```
  - ![螢幕擷取畫面 2024-09-18 164037](https://github.com/user-attachments/assets/54a3928f-83f8-4455-9d11-f30f124a3bf8)
- sudo：臨時取得使用者超級權限
- **使用最高權限賦予"client"操作權限**
  ```
  sudo chown cleint:client /home/client
  ```
  - ![螢幕擷取畫面 2024-09-18 164037](https://github.com/user-attachments/assets/54a3928f-83f8-4455-9d11-f30f124a3bf8)

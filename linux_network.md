# 網路管理：
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

# Linux 基礎操作
## link
- [外部資源](https://linux.vbird.org/linux_basic_train/rockylinux9/unit01.php)
- [積點系統](https://irs.ctlin.tw/dashboard)
- 
## AGENDA
- 列出正在運行的服務資訊
```
ps -l
```
![image](https://github.com/user-attachments/assets/24e4afd4-8cef-4e6b-a87a-5a0608ddeb23)

#### 使用 systemd 的 Fedora 系統執行關閉系統
```
sudo systemctl poweroff
```

#### 使用其他的方式進行關閉系統
```
sudo systemctl halt
```
```
sudo systemctl reboot
```
```
sudo shutdown -c
```

#### 關機選項
```
shutdown --help
```
![image](https://github.com/user-attachments/assets/2d36d052-5b9a-4080-87a8-07359c6fee74)

#### run level
- 常見的運行級別
- 運行級別的標準定義可能會根據不同的 Linux 發行版略有不同，但通常有以下幾個標準的運行級別：
  - 0: 關機（停止系統）
  - 1: 單用戶模式（救援模式，沒有網絡）
  - 2: 多用戶模式（沒有網絡服務，少量進程）
  - 3: 完整的多用戶模式（文本界面，多用戶，多進程，啟動網絡服務）
  - 4: 未定義（通常不使用，系統管理員可以自行配置）
  - 5: 完整的多用戶模式，並啟動圖形界面（常見於桌面系統）
  - 6: 重啟系統


# 用戶管理：
## 介紹
>  系統管理員希望給予某個使用者臨時的管理權限，以便他們可以執行某些管理任務。

> 提高伺服器的安全性,防止遭受惡意攻擊。

> 在企業中不同的部門會有不同的存取權限,可以使用此功能管理使用者訪問權限。

> 最高權限管理員的你,可以監控整個伺服器存取用戶,可以及時發現異常存取的用戶或駭客蹤跡。

- **who:用來看當前的使用者**
```
whoami
```
- ![image](https://github.com/user-attachments/assets/8233ee6a-6491-4e38-a545-834531bb2274)

- **用來看當前的使用者屬於哪一個群組**
```
groups
```
- ![image](https://github.com/user-attachments/assets/a38cbb0d-cc8e-40e6-953b-4878ec2495ec)
- **id:可以用來看當前使用者的帳號資訊所屬群組,帳號id**
```
id
```
- ![image](https://github.com/user-attachments/assets/27c9b649-80e0-4ecc-aec5-5732ef025ad4)

- **getent group sudo:用來看當前的管理員用戶**
```
getent group sudo
```
- ![image](https://github.com/user-attachments/assets/04180199-51c3-443c-9bc6-9027b250905c)

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

- passwd：修改用戶密碼
- usermod：修改使用者資訊

## 實戰演練2
- 描述:使用client身分SSH連線至kali linux並成功在目錄底下創建檔案並刪除檔案最後刪除"client"用戶,並刪除日誌檔

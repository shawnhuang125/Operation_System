# 文件操作：
- ll:顯示檔案資訊
- ll and ls -l 這兩個都是一樣的功能
```
ll
```
```
ls -l
```
- ![image](https://github.com/user-attachments/assets/155e24bc-2741-47b7-883f-4ba4e9a37ed4)

- ls： 上市文件和目錄
```
ls -a
```
![螢幕擷取畫面 2024-09-22 120745](https://github.com/user-attachments/assets/7e73cb71-e808-401e-bb95-4d057ba37362)
```
ls -al
```
- ![螢幕擷取畫面 2024-09-22 120904](https://github.com/user-attachments/assets/bf63c3e9-3b3a-4c32-b26c-203797dfe93a)

- cd： 切換目錄
```
cd /xxx/xxx/xxx/
```
- ![螢幕擷取畫面 2024-09-22 121004](https://github.com/user-attachments/assets/360f23f1-0cf0-4e4f-8603-6cd852089c9a)
- cp：複製檔案或目錄
```
```
- 
- mv：移動文件
```
sudo mv xxxxx [路徑]
```
- ![螢幕擷取畫面 2024-09-22 121929](https://github.com/user-attachments/assets/a9b7494e-f33a-45a8-a10b-f331d5391f01)

- rm：刪除檔案或目錄
- 強制刪除目錄
```
sudo rm -rf xxxxx 
```
- ![螢幕擷取畫面 2024-09-22 122334](https://github.com/user-attachments/assets/73ee57ec-4337-4773-b6f8-80c32f487c09)
- 刪除檔案
```
sudo rm xxxx.xxx
```
- ![螢幕擷取畫面 2024-09-22 121940](https://github.com/user-attachments/assets/63af8235-9bc0-4593-bbe6-5d3a496483df)
- mkdir：建立目錄
```
mkdir xxxxx
```
- ![螢幕擷取畫面 2024-09-22 121123](https://github.com/user-attachments/assets/a15a093d-2d8e-4183-af03-eea1a4a4bc72)
- 
## 實戰演練1
- 描述:新增一個目錄,在目錄底下新增一個txt檔並移動至上層目錄,最後將txt檔和創建的目錄刪除
- 在"Documents/"目錄底下**新增名為"document"的目錄**
- 進入"/home/[user]/Documents/"目錄底下
```
cd /home/[user]/Documents/
```
- ![螢幕擷取畫面 2024-09-22 153317](https://github.com/user-attachments/assets/b63afd2b-a0b5-4b26-a0c8-b1974884ed46)

- **新增目錄**
```
mkdir document
```
- ![螢幕擷取畫面 2024-09-22 121443](https://github.com/user-attachments/assets/fe59d00b-160d-42ce-ad10-ccc8fb85ccd2)

- **確認"document"已建立完成**
```
ls -a
```
- ![螢幕擷取畫面 2024-09-22 121443](https://github.com/user-attachments/assets/c8a7c8ba-3078-451c-a798-e468da9e07f4)
- **進入"document/"目錄**
```
cd /home/[user]/Documents/document/
```
- ![螢幕擷取畫面 2024-09-22 152549](https://github.com/user-attachments/assets/f9634d56-fa3c-476f-a85e-7a501698d3ce)
- **創建一個名為data的txt文件**
```
touch data.txt
```
- ![image](https://github.com/user-attachments/assets/48cd40f5-86b9-4b06-b7ed-afd29d7174e8)
- **寫入txt文檔**
```
echo "文檔內容" > data.txt 
```
- ![螢幕擷取畫面 2024-09-22 152822](https://github.com/user-attachments/assets/2830f8d6-6f3d-4c39-8e1d-b579ef7dbeaf)
- **印出txt檔內容**
```
cat data.txt
```
- ![image](https://github.com/user-attachments/assets/9be61301-c9d1-42d6-9591-08023d42f939)
- **返回上層目錄**
```
cd /home/[user]/Documents/
```
- ![螢幕擷取畫面 2024-09-22 153317](https://github.com/user-attachments/assets/6225b411-6194-4e83-bd19-1c2f0a961819)
- **確認已創建成功**
```
ls 
```
- ![image](https://github.com/user-attachments/assets/a17eebab-1e74-4d63-85ec-fb9eada5f65d)

- **移動名為"document"的目錄至路徑"/home/[user]/Downloads/"**
```
sudo mv document /home/shawn/Downloads/
```
- ![螢幕擷取畫面 2024-09-22 121929](https://github.com/user-attachments/assets/f880d09b-bf8d-4865-a2cc-7b2161fe178a)

- **確認檔案移動成功**
```
ls -a
```
- ![螢幕擷取畫面 2024-09-22 122043](https://github.com/user-attachments/assets/19c3a2ea-d5a4-463f-b718-4c9b42c246fc)

- **刪除目錄**
```
sudo rm -rf document
```
- ![螢幕擷取畫面 2024-09-22 122334](https://github.com/user-attachments/assets/d4efc50d-1003-4ebc-9cd3-7d95a3576cf4)

- **刪除txt檔案**
```
sudo rm data.txt
```
- ![螢幕擷取畫面 2024-09-22 122340](https://github.com/user-attachments/assets/713385e4-f32b-4f59-8817-b5b71aabc8f0)
- **顯示目錄底下檔案是否已刪除**
- ![螢幕擷取畫面 2024-09-22 122348](https://github.com/user-attachments/assets/67921104-2961-41b3-bac2-3a5cc199c570)


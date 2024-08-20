# วิธีใช้งาน OneBox CLI ในการสำรองข้อมูลจาก HOSxP

## 1. ดาวน์โหลดไฟล์โปรแกรม onebox.exe และไฟล์ script onebox-backup.bat 

### onebox.exe ไฟล์โปรแกรม

[คลิกเพื่อ download onebox.exe](https://github.com/onecentric-dev/onebox-cli/releases/latest/download/onebox.exe)


### onebox-backup.bat สำหรับเรียกใช้ใน Windows Task Scheduler
[คลิกเพื่อ download onebox-backup.bat](https://github.com/onecentric-dev/onebox-cli/releases/latest/download/onebox-backup.bat)


## 2. เปิดโฟลเดอร์ที่เก็บไฟล์ onebox.exe

เพื่อความเป็นระเบียบอาจสร้าง Folder ชื่อ OneBox ไว้เก็บ onebox.exe และ onebox-backup.bat ไว้ที่เดียวกัน

<img src="images/1_go_to_directory.png" alt="go_to_directory" width="500">

## 3. ที่แถบไดเรกทอรีด้านบน ลบ Path ออก พิมพ์ `cmd` แล้วกดปุ่ม enter

<img src="images/2_type_cmd.png" alt="type_cmd" width="500">

## 4. ระบบจะเปิด command prompt ในไดเรกทอรีที่เก็บไฟล์ onebox.exe ขึ้นมาให้ ให้ทดสอบโปรแกรมโดยการพิมพ์

```bash
onebox.exe version
```
ถ้าระบบแสดงเลข version ของโปรแกรม หมายถึงระบบทำงานเป็นปกติ

<img src="images/3_type_version.png" alt="type_version" width="500">

## 5. Login เข้าสู่ระบบ 
### 5.1 พิมพ์คำสั่ง login-token ลงในหน้าต่าง command prompt
```bash
onebox.exe login-token
```
ระบบจะถามหา token สำหรับใช้ login สามารถหาได้จากเว็บ [https://hosbox.id.th](https://hosbox.id.th/)

<img src="images/4_login_token.png" alt="login_token" width="500"> <br>

### 5.2 login เข้าสู่เว็บ [https://hosbox.id.th](https://hosbox.id.th/) ด้วย ProviderID

<img src="images/5_go_to_hosbox.png" alt="go_to_hosbox" width="500"> <br>

<img src="images/6_login_provider.png" alt="login_provider_id" width="500">

### 5.3 นำ token จากเว็บ hosbox.id.th ไปใช้ในการ login

คลิกที่ชื่อโปรไฟล์มุมขวาบน

<img src="images/7_get_token_1.png" alt="get_token_1" width="500">

คลิกที่ปุ่ม Onebox token

<img src="images/7_get_token_2.png" alt="get_token_2" width="300">

ระบบจะแสดง OneBox Token ให้คัดลอก และนำไปใช้ในการ Login โดย Token จะมีอายุ 5 นาที และใช้ Login ได้ 1 ครั้งต่อ 1 Token เท่านั้น

<img src="images/7_get_token_3.png" alt="get_token_3" width="500">

นำ Token ที่ได้มากรอกใน command prompt แล้วกดปุ่ม enter

<img src="images/7_get_token_4.png" alt="get_token_4" width="500">

ระบบจะแสดงข้อความ Login successful หาก login สำเร็จ

<img src="images/7_get_token_5.png" alt="get_token_5" width="500">

### 5.4 ตรวจสอบข้อมูล Account 

แสดงข้อมูลองค์กร และแสดงข้อมูล Storage คงเหลือในระบบ onebox โดยใช้คำสั่ง

```bash
onebox.exe account-info
```

<img src="images/8_account_info.png" alt="account_info" width="500">

## 6. ตั้งค่า Line Alert  (ขั้นตอนนี้สามารถทำในภายหลังได้)

พิมพ์คำสั่ง

```bash
onebox.exe alert --set
```

เลือกที่ Line Notify แล้วกดปุ่ม enter

<img src="images/9_set_alert.png" alt="set_alert" width="500">

กรอกข้อมูล Line Token และ ตั้งค่า Alert ID แล้วกดปุ่ม enter หากไม่พบช่องให้กรอก Line Token ให้กดปุ่ม enter อีกครั้ง

`Alert ID` คือ id สำหรับอ้างอิงถึง Setting Alert แต่ละอัน ใช้สำหรับอ้างอิงตอนส่ง Alert กรณีต้องการส่งแบบเฉพาะเจาะจง และใช้อ้างอิงสำหรับการลบ Alert

การกำหนด `Alert ID` สามารถใช้ตัวหนังสือเหล่านี้ได้เท่านั้น 0-9, a-z, A-Z, - , _

<img src="images/9_set_fill_alert.png" alt="set_fill_alert" width="500">

[รายละเอียดเพิ่มเติมเกี่ยวกับการตั้งค่า Alert](https://github.com/onecentric-dev/onebox-cli?tab=readme-ov-file#%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%81%E0%B8%88%E0%B9%89%E0%B8%87%E0%B9%80%E0%B8%95%E0%B8%B7%E0%B8%AD%E0%B8%99)

## 7. แก้ไขไฟล์ onebox-backup.bat

### 7.1 เปิดไฟล์ onebox-backup.bat ด้วย notepad
<img src="images/10_edit_bat.png" alt="edit_bat" width="500">

### 7.2 แก้ไข Path ทั้งหมด 4 ส่วนให้ตรงกับที่จัดเก็บไฟล์ในเครื่อง
<img src="images/10_edit_bat_2.png" alt="edit_bat_2" width="700">

1. path ที่จัดเก็บไฟล์ onebox.exe

2. path ที่เก็บไฟล์ในเครื่อง ที่ต้องการ upload ขึ้นระบบ onebox

3. ชื่อ Folder ที่เก็บไฟล์บนระบบ OneBox (ส่วนนี้จะเปลี่ยน หรือไม่เปลี่ยนก็ได้) <br>
[รายละเอียดเพิ่มเติมเกี่ยวกับการตั้งค่า path บน onebox](https://github.com/onecentric-dev/onebox-cli?tab=readme-ov-file#%E0%B8%AD%E0%B8%B1%E0%B8%9B%E0%B9%82%E0%B8%AB%E0%B8%A5%E0%B8%94%E0%B9%84%E0%B8%9F%E0%B8%A5%E0%B9%8C%E0%B9%82%E0%B8%94%E0%B8%A2%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B9%84%E0%B8%9F%E0%B8%A5%E0%B9%8C%E0%B8%95%E0%B9%89%E0%B8%99%E0%B8%89%E0%B8%9A%E0%B8%B1%E0%B8%9A)

4. path สำหรับเก็บ Log

### 7.3 ตั้งค่า Path เพื่อทดสอบ Upload File

7.3.1 เลือกไฟล์ขนาดเล็กเพื่อทดสอบการ Upload โดยนำ Path File นำมาแทนที่บริเวณกรอบสีแดง (ในตัวอย่างไฟล์ทดสอบคือ `test.txt`)

<img src="images/10_edit_bat_3.png" alt="edit_bat_3" width="700">

7.3.2 ดับเบิ้ลคลิกที่ไฟล์ onebox-backup.bat เพื่อทดสอบการ upload file

<img src="images/10_edit_bat_4.png" alt="edit_bat_4" width="500"> 

ระบบจะแสดง Process การ Upload File

<img src="images/11_test_upload.png" alt="test_upload" width="700">

ตรวจสอบผลการ Upload File บน [https://hosbox.id.th](https://hosbox.id.th)  หากสำเร็จไฟล์จะแสดงขึ้นมาบนหน้าเว็บ

<img src="images/11_test_upload_2.png" alt="test_upload_2" width="500">

## 8. ตั้งค่า Path File ที่เก็บไฟล์ Backup ของโปรแกรม HOSxP

<img src="images/12_edit_path_hosxp_1.png" alt="edit_path_hosxp_1" width="700">

จากตัวอย่าง path `D:\BACKUP` เป็นที่เก็บ Folder 1-31 ที่สร้างจากระบบ HOSxP

<img src="images/12_edit_path_hosxp_2.png" alt="edit_path_hosxp_2" width="500">

เมื่อไฟล์ `onebox-backup.bat` ถูกรัน ระบบจะไปเลือก Folder ให้ตรงกับวันปัจจุบัน และค้นหาไฟล์นามสกุล `.7z` หรือ `.zip` ที่ถูกสร้างในวันนั้น 
และ Upload ขึ้นไปยัง OneBox ใน Folder ที่กำหนด

## 9. ตั้งค่า Windows task scheduler เพื่อรัน `onebox-backup.bat` แบบอัตโนมัติ

### 9.1 เปิดโปรแกรม task scheduler
<img src="images/13_task_1.jpeg" alt="13_task_1" width="500"> <br>

### 9.2 คลิกเลือกเมนู Create Basic Task
<img src="images/13_task_2.jpeg" alt="13_task_2" width="500"> <br>

### 9.3 ตั้งชื่อ Scheduler และกด Next
<img src="images/13_task_3.jpeg" alt="13_task_3" width="500"> <br>

### 9.4 เลือกระยะเวลา Backup เป็น `Daily` แล้วกด Next
<img src="images/13_task_4.jpeg" alt="13_task_4" width="500"> <br>

### 9.5 กำหนดเวลา Backup ควรกำหนดระยะเวลาให้เป็นหลังจากที่ระบบ HOSxP Backup เสร็จ หลังจากนั้นกด Next
<img src="images/13_task_5.jpeg" alt="13_task_5" width="500"> <br>

### 9.6 เลือก Start a program แล้วกด Next
<img src="images/13_task_6.jpeg" alt="13_task_6" width="500"> <br>

### 9.7 เลือกไดเร็คทรอรีเก็บไฟล์ `onebox-backup.bat` หลังจากนั้นกด Next
<img src="images/13_task_8.jpeg" alt="13_task_8" width="500"> <br>

### 9.8 กด Finish
<img src="images/13_task_9.jpeg" alt="13_task_9" width="500"> <br>


## คำสั่งอื่นๆ
### วิธีตั้งค่าให้ลบไฟล์บน OneBox แบบอัตโนมัติกรณีพื้นที่จัดเก็บบน OneBox เต็ม

ให้เพิ่มคำสั่ง `--auto-remove-files-in-folder` เข้าไปต่อท้ายในไฟล์ onebox-backup.bat

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP" -d "HOSxP-Backup" --send-alerts --log --log-file "C:\OneBox\log" --hosxp --auto-remove-files-in-folder
```

เมื่อพื้นที่จัดเก็บไม่เพียงพอต่อการ Upload ระบบจะทำการลบไฟล์ที่เก่าที่สุดใน Folder ที่กำหนด ในตัวอย่างจะเป็น Folder ชื่อ HOSxP-Backup เพื่อให้การ Backup ทำได้ต่อเนื่อง

### กรณี Folder ที่ใช้เก็บไฟล์ Backup บน HOSxP เป็น Folder เดียว ไม่ได้แยก Folder 1-31

ให้แก้ไขไฟล์ onebox-backup.bat เปลี่ยน `--hosxp` เป็น `--hosxp-one-folder`

```
"C:\OneBox\onebox.exe" push -s "D:\BACKUP" -d "HOSxP-Backup" --send-alerts --log --log-file "C:\OneBox\log" --hosxp-one-folder
```








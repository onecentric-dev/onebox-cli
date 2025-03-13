# การตั้งค่า Notify OneBox CLI (เวอร์ชั่น 1.2.2 ขึ้นไป)

## 1. ดาวน์โหลดไฟล์โปรแกรมเวอร์ชั่นล่าสุด

ดาวน์โหลดไฟล์ OneBox สำหรับ Windows

[คลิกเพื่อ download สำหรับ Windows](https://github.com/onecentric-dev/onebox-cli/releases/latest/download/onebox.exe)

ดาวน์โหลดไฟล์ OneBox สำหรับ Linux
```bash
sudo wget https://github.com/onecentric-dev/onebox-cli/releases/latest/download/onebox -O /usr/local/bin/onebox
```

ให้สิทธิ์ในการรันไฟล์ OneBox สำหรับ Linux
```bash
sudo chmod +x /usr/local/bin/onebox
```



## 2. เปิดโฟลเดอร์ที่เก็บไฟล์ onebox.exe เดิม (สำหรับ Windows)

<img src="images/1_folder_program.png" alt="folder_program" width="700">

## 3. ลบไฟล์โปรแกรมเดิม แล้วแทนที่ด้วยโปรแกรมเวอร์ชั่นล่าสุด (สำหรับ Windows)

<img src="images/2_move_prgram.png" alt="move_prgram" width="700">

## 4.เปิด command prompt และตรวจสอบเวอร์ชั่นโปรแกรม

```bash
onebox version
```
โปรแกรมต้อง version เท่ากับหรือมากกว่า 1.2.2

<img src="images/3_onebox_version.png" alt="onebox_version" width="500">

## 5.ทำการ Logout และ Login เข้าสู่ระบบ
### 5.1 พิมพ์คำสั่ง logout ลงในหน้าต่าง command prompt
```bash
onebox logout
```
### 5.2 พิมพ์คำสั่ง login-token ลงในหน้าต่าง command prompt เพื่อเข้าสู่ระบบอีกครั้ง
```bash
onebox login-token
```
ระบบจะถามหา token สำหรับใช้ login สามารถหาได้จากเว็บ [https://hosbox.id.th](https://hosbox.id.th/)

<img src="images/4_login_token.png" alt="login_token" width="500"> <br>

### 5.3 login เข้าสู่เว็บ [https://hosbox.id.th](https://hosbox.id.th/) ด้วย ProviderID

<img src="images/5_go_to_hosbox.png" alt="go_to_hosbox" width="500"> <br>

<img src="images/6_login_provider.png" alt="login_provider_id" width="500">

### 5.4 นำ token จากเว็บ hosbox.id.th ไปใช้ในการ login

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

### 5.5 ตรวจสอบข้อมูล Account 

แสดงข้อมูลองค์กร และแสดงข้อมูล Storage คงเหลือในระบบ onebox โดยใช้คำสั่ง

```bash
onebox account-info
```

<img src="images/8_account_info.png" alt="account_info" width="500">

## 6. ตรวจสอบการตั้งค่า Notify
### 6.1 พิมพ์คำสั่งสำหรับตรวจสอบการตั้งค่า Notify ทั้งหมด
```bash
onebox alert --list
```
ระบบจะแสดง Notify ที่เราตั้งค่าทั้งหมด

<img src="images/4_onebox_alert_list.png" alt="alert_list" width="500"> <br>

### 6.2 ลบ Notify ประเภท line-notify ด้วย Alert ID (หากมี)

<img src="images/5_remove_alert.png" alt="remove_alert" width="500">

### 6.3 พิมพ์คำสั่งสำหรับตั้งค่า Notify

```bash
onebox alert --set
```
<br>
Notify ที่เพิ่มมาจะมี Email, Discord Webhook และ Telegram
<br>
<img src="images/6_alert_set.png" alt="alert_set" width="800">
<br><br>
Email - กรอก Email ที่ต้องการส่งแจ้งเตือน Backup
<br>
<img src="images/6_alert_set_email.png" alt="alert_set_email" width="900">
<br><br>
Discord Webhook

<img src="images/6_alert_set_discord.png" alt="alert_set_discord" width="900">

#### การสร้างเซิร์ฟเวอร์และขอ Discord Webhook URL

กดเครื่องหมาย `+` สำหรับสร้างกลุ่มสำหรับแจ้งเตือน

<img src="images/alert/set-discord-1.png" alt="set-discord-1" width="600">

กด `สร้างของฉัน`

<img src="images/alert/set-discord-2.png" alt="set-discord-2" width="400">

กด `สำหรับฉันและเพื่อนๆ`

<img src="images/alert/set-discord-3.png" alt="set-discord-3" width="400">

ตั้งชื่อเซิร์ฟเวอร์ แล้วกด `สร้าง` แล้วกด `แก้ไขช่อง`

<img src="images/alert/set-discord-4.png" alt="set-discord-4" width="400">

คลิกขวาช่องข้อความที่ต้องการแจ้งเตือน เช่น `#ทั่วไป` แล้วกด `แก้ไขช่อง`

<img src="images/alert/set-discord-5.png" alt="set-discord-5" width="400">

กด `การรวม` และกด `สร้าง Webhook`

<img src="images/alert/set-discord-6.png" alt="set-discord-6" width="600">

กดที่ตัว bot เพิ่อแสดงรายละเอียด

<img src="images/alert/set-discord-7.png" alt="set-discord-7" width="600">

กด `คัดลอก URL เว็บฮุก` เพื่อนำไปใช้ตั้งค่าการแจ้งเตือน โดย Discord Webhook URL จะขึ้นต้นด้วย `https://discordapp.com/api/webhooks` หรือ `https://discord.com/api/webhooks`

<img src="images/alert/set-discord-8.png" alt="set-discord-8" width="600">

กรอก URL Discord Webhook ที่ต้องการส่งแจ้งเตือน Backup กด enter และตั้ง Alert ID เช่น discord01 แล้วกด enter

<img src="images/6_alert_set_discord.png" alt="alert_set_discord" width="600">

<br><br><br>

Telegram - กรอก Chat ID ที่ต้องการส่งแจ้งเตือน Backup

<img src="images/alert/alert-set-telegram.png" alt="alert-set-telegram" width="650">

#### การสร้างกลุ่มและขอ Chat ID

เปิดโปรไฟล์แล้วกด `New Group` สำหรับสร้างกลุ่มสำหรับแจ้งเตือน

<img src="images/alert/set-telegram-1.png" alt="set-telegram-1" width="400">

ตั้งชื่อกลุ่มสำหรับการ backup แล้วกด `Next`

<img src="images/alert/set-telegram-2.png" alt="set-telegram-2" width="400">

เพิ่ม bot Hos Box Notify โดยพิมพ์ `@HosBox_notify_bot` กดที่ชื่อ bot แล้วกด `Create`

<img src="images/alert/set-telegram-3.png" alt="set-telegram-3" width="400">

เมื่อกลุ่มถูกสร้างให้พิมพ์ `/id` เพื่อแสดง Chat ID สำหรับนำไปใช้ตั้งค่าการแจ้งเตือน โดยจะขึ้นต้นด้วย - ตามด้วยตัวเลข เช่น `-1234567890`

<img src="images/alert/set-telegram-4.png" alt="set-telegram-4" width="600">

กรอก Chat ID ที่ต้องการส่งแจ้งเตือน Backup กด enter และตั้ง Alert ID เช่น telegram01 แล้วกด enter

<img src="images/alert/alert-set-telegram.png" alt="alert-set-telegram" width="600">

### 6.4 พิมพ์คำสั่งสำหรับตรวจสอบการตั้งค่า Notify ทั้งหมดอีกครั้ง
```bash
onebox alert --list
```

<img src="images/7_alert_list.png" alt="7_alert_list" width="500">

หากข้อมูลถูกต้องแล้วถือว่าการตั้งค่าการแจ้งเตือนเสร็จสิ้น
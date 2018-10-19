# Braille display


## Feature 
  - โหมด Notepad 
    - พิมพ์ข้อความยาวไม่เกิน 102 บรรทัด บรรทัดละไม่เกิน 40 ตัวอักษร
    - `ออกจากโหมด` notepad โดยกด `(space + e)`
    - `บันทึกไฟล์`โดยการปุ่ม `(space + s)` หน้าจอแสดงผลจะแสดง name:/_ ทำหรับพิมพ์ชื่อไฟล์
    - ไฟล์ที่ได้จากการบันทึกเป็น .tbt
  - โหมดอ่าน
    -	รับรองไฟล์ tbt,brf,txt
    -	ไฟล์ tbt, brf ,txt จะต้องทำการแปลงเป็น unicode จากโปรแกรม BrailleConverter หรือ Duxburyหรือ tbt
    -	สามารถแสดงรายการไฟล์ใน Sd card สามารถเข้าโฟลเดอร์เพื่อดูรายการไฟล์ต่างๆได้
    -	รับรองไฟล์ 20 และ 40 ตัวอักษร (ในแค่ละบรรทัด)
    - ค้นหาไฟล์ TBT,BRF,TXT ใน SD-Card ได้
    
  - โหมดบลูทูธ
    - เชื่อมต่อกับอุปกรณ์ android ทำงานเป็น navigator 
    - Read text ด้วย Talkback และแสดงผ่านจุดเบรลล์
    - Keyboard Braille  
    - โหมดพิมพ์ เป็นแป้นพิมพ์อักษรเบรลล์

## การควบคุม
- โหมดอ่าน
  -	เลื่อนจอนขวา หรือ กด `Enter` เพื่อเข้าอ่านไฟล์ หรือโฟลเดอร์
  -	เลื่อนจอยซ้ายเพื่อออกจากโฟลเดอร์ หรือ กดเข้าโฟลเดอร์ `..` เพื่อย้อนกลับ
  -	เลื่อนจอยลงเพื่อเลือกไฟล์ถัดไป หรืออ่านข้อความบรรทัดถัดไป
  -	เลื่อนจอยขึ้นเพื่อเลือกไฟล์ก่อนหน้า หรืออ่านข้อความบรรทัดก่อนหน้า
  -	กดปุ่มขวาเพื่ออ่านข้อความในบรรทัด (ข้อความถัดไปในบรรทัด) 
  -	กดปุ่มซ้ายเพื่ออ่านข้อความในบรรทัด (ข้อความก่อนหน้าในบรรทัด) 
  -	`Space + e` เพื่อออกจากการอ่าน

## สิ่งที่ยังแก้ไม่ได้ 
  - โหมด notepad เหลือทำให้รับรองความยาวเกิน 4096 และเอาไปใส่ในรอม 
  - ความยาวในโหมดพิมพ์ยังไม่เกิน 97*40 ตัวอักษร ต้องเอาเก็บไว้ในรอม

## ✖ ที่ต้องแก้ไข 
  - บัคในโหมดอ่านไฟล์ เมื่ออ่านไฟล์เสร็จสิ้นจะมีตัวอักษรเกินขึ้นมา 1 ตัวในบรรทัดแรก ตำแหน่งที่ 1 โดยไม่รู้สาเหตุ 
    - #### วิธีการเจอบัคนี้
      - หาไฟล์ลง SD-card เป็น tbt txt brf ก็ได้
      - ทำการผ่านไฟล์จาก read > เลือกไฟล์ > เปิดอ่าน
      - หลังจากพร้อมสำหรับการผ่าน สังเกตที่บรรทัดแรก (หลังจากเตรียมการอ่านไฟล์เสร็จจะแสดงบรรทัดแรก) ตัวอักษรตำแหน่งที่ 1 `ปล. บางครั้งจะไม่แสดง`
  - ไม่มีฟังก์ชั่นจัดการไฟล์ (ตอนนี้ลบได้อย่างเดียว)
## 🗹 ปัญหาที่แก้ไขแล้ว  
  - ในโหมดอ่านไฟล์ หากบรรทัดก่อนหน้าเว้บว่าง หรือเป็นเครื่องหมาย line feed \r\n จะไม่สามารถย้อนกลับได้ต้องแก้ไขที่อัลกอริทึม
  - สระภาษาไทยยังไม่ได้ทดสอบ
  - ยังไม่ได้รวมบันทึกไฟล์ 
  - บันทึกไฟล์ที่พิมพ์ในโหมด notepad 
  - ก-ฮ แสดงถูกต้อง
  - a-z แสดงถูกต้อง 
  - ปรับความเร็ว Serial3  เป็น 115200
  - แก้อาการค้างเมื่อค้นหาไฟล์
  - ย้อนกลับจากโหมดอ่านไม่ได้ ต้องรีเซ็ท
  - ยังเปิดและดูไฟล์ในโฟลเดอร์ไม่ได้
  - ไม่สามารถปรับ baud rate จาก 9600 115200 ขณะรันโปรแกรม ใน STM32 ได้
  - อ่านไฟล์ช้ามากๆ
  - Refresh dot ช้าา
  - อ่านไฟล์ sector ถัดไป Charator>4096 
  - เลื่อนบรรทัด ไป/กลับ (ไม่เกิน 4096 ตัวอักษร)
#### Serial config 
```c
  //9600 connect to bluetooth module
  UART4_Configuration(); 
  //115200 connect with keyboard
  USART2_Configuration(); 
  //115200 defualt serial
  USART1_Configuration();
  //115200 connect to ch376 (sd card module)
  USART3_Configuration();
```

#### Output Function
```c
   //ส่ง Braille unicode ไปแสดงที่จุดเบรลล์
   printDot(brailleUnicodeByte, sizeof(brailleUnicodeByte)); 
   // ส่งสตริงไปแสดงที่จุดเบรลล์
   stringToUnicodeAndSendToDisplay("String here"); 
    // ส่งสตริงยาว 40 ตัวอักษร params(สตริงยาว<=40, 0 หรือ 1)
   printStringLR("String", 0);
    //beep sound 
    ส่งออก Serial2 
```
Serial 2 command [Docs here](https://github.com/moomdate/Bkeyboard/blob/master/readme.md)




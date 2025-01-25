# Trunk-Based Development Workshop

### Step 1: Create new repo by forking repo.
#### สมาชิกคนที่ A Repo Owner
---
1. เข้า GitHub ด้วยบัญชีของตนเอง, แล้วค้นหา repo ที่ชื่อว่า `cs_github_tbd`
2. ทำการ Fork repo
3. ทำการเพิ่มสมาชิกคนอื่นเข้าสู่ repo
4. ทำการ clone repo จาก GitHub(remote) ลงมาที่ Computer(local) ของตัวเอง
5. ย้าย directory ไปยัง repo ที่พึ่ง clone มา  

#### สมาชิกคนที่ B และ C Collaborator
---
1. รับคำเชิญจากสมาชิกคนที่ A เพื่อเข้า repo เดียวกันในกลุ่ม
2. ทำการ clone repo จาก GitHub(remote) ลงมาที่ Computer(local) ของตัวเอง
3. ย้าย directory ไปยัง repo ที่พึ่ง clone มา


### Step 2: Edit another file.
        
#### สมาชิกคนที่ A 
---
1. แก้ไข file ชื่อ greeting_a.py โดยทำการเพิ่ม print ชื่อตัวเองลงไปบน code ในบรรทัดที่ 
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง

```shell
    $ git add . && git commit -m "create greeting from A"
```

3. จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง 

```shell
    $ git push
```

#### สมาชิกคนที่ B
---
1. แก้ไข file ชื่อ greeting_b.py โดยทำการเพิ่ม print ชื่อตัวเองลงไปบน code
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง 

```shell
    $ git add . && git commit -m "create greeting from B"
```

3. **รอ A push ก่อน** จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง

```shell
    $ git push
```

- `ถ้าเกิด error ขึ้นแปลว่าถูก`  
4. Update local file ด้วยคำสั่ง

```shell
    $ git pull
```


#### สมาชิกคนที่ C
---
1. แก้ไข file ชื่อ greeting_c.py โดยทำการเพิ่ม print ชื่อตัวเองลงไปบน code
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง 

```shell
    $ git add . && git commit -m "create greeting from C"
```

3. **รอ B push ก่อน** จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง 

```shell
    $ git push
```

- `ถ้าเกิด error ขึ้นแปลว่าถูก`  
4. Update local file ด้วยคำสั่ง

```shell
    $ git pull
```

### Step 3: Edit same file, But difference part.
1. ให้แต่ละคนแก้ไข file ชื่อ my_operator.py โดยทำการแก้ไขให้ function ทำงานได้
2. ให้ B เป็นคน push ขึ้นไปก่อน โดยที่แต่ละคนยังไม่ต้อง commit ใดๆ
3. ให้ A ทำการ pull
4.

```shell
    $ git add . && git commit -m "create greeting from A"
```

3. จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง 

```shell
    $ git push
```
1. Update file บนเครื่องให้เหมือนบน GitHub โดยใช้คำสั่ง 

```shell
    $ git pull
```

2. จากนั้นทำการแก้ไข conflict โดยใช้คำสั่ง 

```shell
    $ git merge main
```

3. เปิด vscode(editor) เพื่อใช้สำหรับแก้ conflict แล้วเลือกหัวข้อ Source control ในแถบด้านซ้ายมือ จากนั้นเลือก file ที่มี conflict แล้วทำการแก้ไข

4. โดยวิธีการแก้คือให้เลือกว่าจะส่วนไหน
    - ถ้าอยากได้ code ที่เราเขียนเอง ให้เลือก `Accept Current`
    - ถ้าอยากได้ code จากบน remote ให้เลือก `Accept Incoming`

5. จากนั้นทำการบันทึกการเปลี่ยนแปลงนั้นด้วยคำสั่ง

```shell
    $ git commit -m "<ข้อความอธิบายการแก้ไข>"
```

6. จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง 

```shell
    $ git push
```

### Step 4: Edit same file, But same part.


### Exercise: จำลองสถานณ์การการแก้ Conflict โดยให้คนในทีมช่วยกันแก้ไข file  ชื่อ script.js โดยเพิ่มคำสั่งที่ทำให้สามารถแสดงชื่อของทุกคนในกลุ่มได้ โดยมีข้อกำหนดดังนี้
- ใช้คำสั่ง console.log() 
- ใน 1 commit สามารถเพิ่ม log ได้ทีละคน
- ต้องทำให้เกิด conflict และ แก้ conflict นั้นด้วยการ merge

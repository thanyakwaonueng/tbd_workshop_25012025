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
1. แก้ไข file ชื่อ style.css โดยแก้ color จาก red เป็น green
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง

```shell
    $ git add . && git commit -m "Change color red to green"
```

3. จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง 

```shell
    $ git push
```

#### สมาชิกคนที่ B (ถ้ามีคนที่ C ทำแบบเดียวกับคนที่ B)
---
1. แก้ไข file ชื่อ style.css โดยแก้ color จาก red เป็น blue
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง 

```shell
    $ git add . && git commit -m "Change color red to blue"
```

3. **รอคนที่ A push ก่อน** จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repo ด้วยคำสั่ง git push
        หากสมาชิกคนที่ B และ C เกิด error แปลว่าเกิด conflict เรียบร้อยให้ทำ Step 3 ต่อได้เลย ถ้าไม่ให้ทำซ้ำอีกรอบ


### Step 3: Edit same file, But difference part.
#### สมาชิกคนที่ B (ถ้ามีคนที่ C รอคนที่ B ทำเสร็จก่อน แล้วทำแบบเดียวกับคนที่ B)
---
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

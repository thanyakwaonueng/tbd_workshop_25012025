# Trunk-Based Development Workshop

### Step 1: Create new repository
สมาชิกคนที่ 1 Repo Owner
---
1. เข้า GitHub ด้วยบัญชีของตนเอง, แล้วค้นหา repository ที่ชื่อว่า `cs_github_tbd`
2. ทำการ Fork repository
3. ทำการเพิ่มสมาชิกคนอื่นเข้าสู่ repository
4. ทำการ clone repository จาก GitHub(remote) ลงมาที่ Computer(local) ของตัวเอง
5. ย้าย directory ไปยัง repository ที่พึ่ง clone มา
   
สมาชิกคนที่ 2 และ 3 Collaborator
---
1. รับคำเชิญจากสมาชิกคนที่ 1 เพื่อเข้า repository เดียวกันในกลุ่ม
2. ทำการ clone repository จาก GitHub(remote) ลงมาที่ Computer(local) ของตัวเอง
3. ย้าย directory ไปยัง repository ที่พึ่ง clone มา


### Step 2: Create conflict
        
สมาชิกคนที่ 1 
---
1. แก้ไข file ชื่อ style.css โดยแก้ color จาก red เป็น green
2. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง

```shell
    git add . && git commit -m "Change color red to green"
```

3. จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repository ด้วยคำสั่ง git push
สมาชิกคนที่ 2 **ถ้ามีคนที่ 3 ทำแบบเดียวกับคนที่ 2
4. แก้ไข file ชื่อ style.css โดยแก้ color จาก red เป็น blue
5. ทำการบันทึกการเปลี่ยนแปลง file โดยใช้คำสั่ง 
```shell
    git add . && git commit -m "Change color red to blue"
```
6. **รอคนที่ 1 push ก่อน** จากนั้นทำการเปลี่ยนแปลงการแก้ไขขึ้นไปบน remote repository ด้วยคำสั่ง git push
        หากสมาชิกคนที่ 2 และ 3 เกิด error แปลว่าเกิด conflict เรียบร้อยให้ทำ Step 3 ต่อได้เลย ถ้าไม่ให้ทำซ้ำอีกรอบ


### Step 3: Resolve conflict
สมาชิกคนที่ 2
---
1. Update file บนเครื่องให้เหมือนบน GitHub โดยใช้คำสั่ง git pull
2. จากนั้นเลือก

Exercise: จำลองสถานณ์การการแก้ Conflict โดยมีข้อกำหนดดังนี้
1. แก้ไฟล์เดียวกัน

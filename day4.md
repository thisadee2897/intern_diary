# วันพฤหัสบดี ที่ 26 พฤศจิกายน 2563
วันนี้ลุยโจทย์ทั้งวันเลยครับผม
วันนี้มีโจทย์ไหนบ้าง มาดูเลยครับ
ข้อแรก ระดับที่ 7

### How many consecutive numbers are needed?
https://www.codewars.com/kata/559cc2d2b802a5c94700000c
เฉลยจากพี่เบนครับ เพราะมันเที่ยงแล้ว ถ้าไม่บอกผม คงได้นั่งถึงเย็นแน่ๆ 
```python
def spin_words(sentence):
    nums = sorted(arr)
    hide_num = 0   
    for lead, follow in zip(nums[:-1],nums[1:]):
        if  lead != follow:
            hide_num += follow - lead - 1
    return hide_num
```
แล้วผมก็อยากลองทำในรูปแบบที่ยังเป็น enumerate เลยแกะอัลกอลิทึมจากพี่เบนครับ หาทางทำจนได้ ในกรณีที่ไม่ได้ใช้ zip 
```python
def consecutive(arr):
    nums = sorted(arr)
    hide_num = 0
    for i, n in enumerate(nums[:-1]):
        if nums[i] != nums[i+1]-1:
            hide_num += (nums[i+1]-nums[i]) - 1
    return hide_num
```


โจทย์ตอนบ่ายนี้ก็ลองๆทำเองครับ แต่เลือกทำระดับแปด เพราะคิดว่าของที่ง่ายๆมาอยู่ระดับนี้หมดแล้วล่ะ
ผมก็ทำได้เองเฉยเลย 
ข้อนี้ครับ 
### Square(n) Sum
ลิงค์โจทย์ https://www.codewars.com/kata/515e271a311df0350d00000f
นี่คำตอบที่ผมคิดครับ แต่พอรันผ่านแล้วไปดูแนวคิดของคนอื่น มีแต่คนคิดเจ๋งๆ แล้วก็ผมก็ยังงแนวคิดเขาอยู่บ้าง
```python
def square_sum(numbers):
    number = []
    for i in numbers:
        n = i**2
        number.append(n)
    x=sum(number)
    return x
```


ต่อมานี้ง่ายมากๆ ทำไมไม่เจอตั้งแต่วันแรกไม่รู้ 555555 

### Function 2 - squaring an argument
https://www.codewars.com/kata/523b623152af8a30c6000027

ผมเขียนแบบที่ผมเข้าใจอ่ะเนาะ  ทีแรกไม่อยากเชื่อว่าจะผ่าน 
```python
def square_sum(numbers):
    def square(n):
    return n**2
```


และโจทย์นี้เอางงเหมือนกัน แต่ก็ยังได้อยู่นะครับ
### Reversed Words
https://www.codewars.com/kata/51c8991dee245d7ddf00000e
```python
def reverseWords(s):
    x =s.split(" ")
    y = x[::-1]
    z=" "
    return (f"{z.join(y)}")
```
โจทย์นี้ ระดับ5 เหมือนง่ายนะ เลยลองดู ตั้งแต่สี่โมงเย็นจนจะนอนแล้ว ผมยังทำไม่ได้เลยครับ
Rot13
https://www.codewars.com/kata/530e15517bc88ac656000716/train/python
แต่นิสัยติดตัวผมคือ ไม่ยอมหนีง่ายๆหรอกครับ จะหาทางจนกว่าจะได้ ไม่รู้ว่าวันไหนนะ :D


คำศัพท์วันนี้ผม เพิ่มไป 17  คำได้จากโจทย์ ที่ผมไม่รู้ความหมาย ผมก็ทยอยเพิ่มเรื่อยๆ เวลาว่างๆ ก่อนนอน แล้ว ก่อนออกมาฝึกงาน ก็เปิดอ่าน พยายามทำบ่อยๆ ซักวันต้องเป็นนิสัย 
ผมขออาบน้ำนอนก่อน ตอนนี้เวลา 23:06 ฝันดีครับ
# Javascript Basic() {

**บทความ Javascript เบื้องต้น ใช้ภาษาที่น่าจะเข้าใจกันได้ง่าย By [Heng Indy Anvil](https://www.facebook.com/LaDscaLEs)
> บทความเหมาะสำหรับผู้ที่ยังไม่มีความรู้หรือยังไม่ค่อยมีความรู้ทางด้าน Programming               โดยตั้งใจว่าจะเขียนปูพื้นไปเรื่อย ๆ ก่อน จนคิดว่าพอสมควรแล้ว จะขยับไปทางด้าน angularjs

## Table of Contents
  1. [Type](#type)
  1. [Reference](#reference)
  1. [Function](#function)

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Type
  ชนิดของตัวแปรใน Javascript นั้น จากที่ผมได้พัฒนา Web Applicationได้เจออะไรแปลก ๆ มาพอสมควร งั้นผมจะแจกแจงที่ละตัวเลยนะครับ
  1. [string]() (ตัวอักษร)
    เอาไว้เก็บข้อมูลจำพวก ข้อความ, ตัวอักษร ใน Javascript นั้น การกำหนดข้อความต้องทำสัญลักษณ์เปิดและปิด ทำได้ 2 แบบ คือ
    - single quote(') ตัวอย่าง "Heng Indy Anvil", "123456", "♥"
    - double quote(") ตัวอย่าง 'Heng Indy Anvil', '123465', '♥'
  1. [number]() (ตัวเลข)
    เอาไว้เก็บข้อมูลจำพวก ตัวเลข ทั้งหมด ทั้งจำนวนเต็ม จำนวนจริง ตัวอย่าง
    ```javascript
    -12, 0, 125, 64.15
    ```
    
  1. [boolean]() (เท็จจริง)
    เอาไว้เก็บข้อมูลจำพวก ค่าเท็จจริง ตัวอย่าง
    ```javascript
    true, false
    ```
    
  1. [date]() (วัน)
    เอาไว้เก็บข้อมูลจำพวก วัน ตรงตัวมาก ๆ เลย ตัวอย่าง
    ```javascript
    'Fri Dec 25 2015 09:45:16 GMT+0700 (SE Asia Standard Time)'
    ```
    
  1. [array]() (ช่องเก็บของ)
    เอาไว้เก้บข้อมูลจำพวก ชนิดเดียวกัน แต่เก็บไว้เป็นจำนวนมาก (ให้มองเหมือนลังเบียร์ที่ข้างในมีช่องไว้ใส่ขวด) ตัวอย่าง 
    ```javascript
    [0,1,2]
    ["a","b",'c']
    ```
    
  1. [object]() (เลโก้)
    เอาไว้เก็บข้อมูลจำพวก เอาหลาย ๆ อย่างมาต่อมารวมกัน เป็นก้อนข้อมูลขนาดใหญ่ก็ได้ เหมือนกับว่า เรามี Flow Chart ตรงกลางอยู่ 1 อัน เราจะโยงเพื่อเพิ่มข้อมูลว่าอันนี้ มันอยู่ในนี้นะ โดยแต่ละอันจะมีข้อมูลของมันเองอยู่ด้วย ตัวอย่าง 
    ```javascript
    hia = {
      name: "Heng Indy Anvil",
      age: 99,
      isDead: false,
      birthday: new Date('Fri Dec 25 2015 09:45:16 GMT+0700 (SE Asia Standard Time)'),
      numberlike: [1,2,9],
      other: {
        tel: '089-999-9999',
        phone: 'i-phone'
      }
    }
    ```
    
  1. [global]() (window)
    หลายคนอาจจะสับสนว่าทำไมมี global มีนเป็นชื่อเรียกของตัวแปรอิสระอยู่บนสุดของพวก Class แต่ในนี้ไม่ใช่ทุกหน้า Page จะมีตัวแปร window อยู่เสมอ ๆ ซึ่ง window มีคุณสมบัติเป็น object แต่ชื่อเรียกจริง ๆ เมื่อทำงานตรวจสอบ Type จะได้เป็น Global
    ```javascript
    Window {external: Object, chrome: Object, document: document, CustomElements: Object, _perfRefForUserTimingPolyfill: Performance…}
    ```
    
  1. [function]() (บทบาท, การทำงาน)
    เป็นรูปแบบในการสั่งทำงาน เหมือนใบสั่งเมื่อเราประกาศว่ามีใบสั่งแบบนี้นะ แล้วเอามาใช้ ดังนั้นการทำงานในใบสั่งจึงเกิดขึ้น
    ```javascript
    function talkDate() {
      /**
       * เขียยใบสั่ง talkDate ขึ้นมา
       * โดยให้มีการทำงาน คือ แสดงค่า วันที่ปัจจุบันออกมา
       */
      console.log(new Date())
    }
    /**
     * ใช้ใบสั่ง talkDate ให้ทำงานได้
     */
    talkDate();
    ```
  
## Reference
  1. dsfsdf

## Function
  1. dsfsdf
  
# };

# Javascript Basic() {

**บทความ Javascript เบื้องต้น ใช้ภาษาที่น่าจะเข้าใจกันได้ง่าย By [Heng Indy Anvil](https://www.facebook.com/LaDscaLEs)
> บทความเหมาะสำหรับผู้ที่ยังไม่มีความรู้หรือยังไม่ค่อยมีความรู้ทางด้าน Programming               โดยตั้งใจว่าจะเขียนปูพื้นไปเรื่อย ๆ ก่อน จนคิดว่าพอสมควรแล้ว จะขยับไปทางด้าน angularjs

## Table of Contents
  1. [Type](#type)
  1. [Check Type](#check-type)
  1. [Reference](#reference)
  1. [Function](#function)

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Type
  ชนิดของตัวแปรใน Javascript นั้น จากที่ผมได้พัฒนา Web Applicationได้เจออะไรแปลก ๆ มาพอสมควร งั้นผมจะแจกแจงที่ละตัวเลยนะครับ
  1. [string](#type) (ตัวอักษร)
    เอาไว้เก็บข้อมูลจำพวก ข้อความ, ตัวอักษร ใน Javascript นั้น การกำหนดข้อความต้องทำสัญลักษณ์เปิดและปิด ทำได้ 2 แบบ คือ
    - single quote(') ตัวอย่าง "Heng Indy Anvil", "123456", "♥"
    - double quote(") ตัวอย่าง 'Heng Indy Anvil', '123465', '♥'
  1. [number](#type) (ตัวเลข)
    เอาไว้เก็บข้อมูลจำพวก ตัวเลข ทั้งหมด ทั้งจำนวนเต็ม จำนวนจริง ตัวอย่าง
    ```javascript
    -12, 0, 125, 64.15
    ```
    
  1. [boolean](#type) (เท็จจริง)
    เอาไว้เก็บข้อมูลจำพวก ค่าเท็จจริง ตัวอย่าง
    ```javascript
    true, false
    ```
    
  1. [date](#type) (วัน)
    เอาไว้เก็บข้อมูลจำพวก วัน ตรงตัวมาก ๆ เลย ตัวอย่าง
    ```javascript
    'Fri Dec 25 2015 09:45:16 GMT+0700 (SE Asia Standard Time)'
    ```
    
  1. [array](#type) (ช่องเก็บของ)
    เอาไว้เก้บข้อมูลจำพวก ชนิดเดียวกัน แต่เก็บไว้เป็นจำนวนมาก (ให้มองเหมือนลังเบียร์ที่ข้างในมีช่องไว้ใส่ขวด) ตัวอย่าง 
    ```javascript
    [0,1,2]
    ["a","b",'c']
    ```
    
  1. [object](#type) (เลโก้)
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
    
  1. [global](#type) (window)
    หลายคนอาจจะสับสนว่าทำไมมี global มีนเป็นชื่อเรียกของตัวแปรอิสระอยู่บนสุดของพวก Class แต่ในนี้ไม่ใช่ทุกหน้า Page จะมีตัวแปร window อยู่เสมอ ๆ ซึ่ง window มีคุณสมบัติเป็น object แต่ชื่อเรียกจริง ๆ เมื่อทำงานตรวจสอบ Type จะได้เป็น Global
    ```javascript
    Window {external: Object, chrome: Object, document: document, CustomElements: Object, _perfRefForUserTimingPolyfill: Performance…}
    ```
    
  1. [function](#type) (บทบาท, การทำงาน)
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
  
  1. [null](#type) (ค่าที่ไม่รู้)
    เป็นข้อมูลที่ไม่รู้ค่า ไม่มีใช่มีค่านะ แต่เป็นข้อมูลที่เอาไปใช้อะไรไม่ได้ ยิ่งกว่าขยะอีก(แบบใส่อารมณ์หน่อย ๆ) เหมือนการที่เรากรอกแบบฟอร์มไม่ครบ แต่คนนำใบเราไปทำสถิติแล้วดันไม่มีแต่จำเป็นต้องใส่ข้อมูลอะไรลงไปบางอย่าง ซึ่งไม่สามารถนำไปใช้อะไรได้

  1. [undefined](#type) (ไม่มีค่า)
    ตรงตัวตรง ไม่มีข้อมูล ไม่มีค่า

  1. [this](#type) (ค่า ณ จุดนั้น)
    this ตรงปกติ ถ้าเป็นภาษา VB เป็น Me ซึ่งดูการใช้คำมันสื่อมาก คือ เป็นค่าของมันเอง เหมือนกับเวลาคนทั้งโลกจะกำหนดชื่อเรียกเราเป็นชื่อจริง แต่พอเข้ามาในบ้าน คนในบ้านอาจจะกำหนดชื่อเราเป็นชื่อเล่นในการเรียกใช้ก็ได้ หรือถ้าคนในบ้านไม่ได้กำหนดในการเรียก ก็ใช้ชื่อจริงนั้นแหละในการเรียกหา ซึ่งมีคุณสมบัติเป็น object
    จากตัวอย่างข้างใต้จะเห็นว่า this ที่ใช้ครั้งแรก คือ ระยะข้อมูลสูงสุดของหน้า Page จึงเป็น window ออกมา พอเราสร้าง Function ขึ้นมา แล้วเรียก this ออกมา ซึ่งตามปกติ this ที่เรียกออกมานั้น คือ ระยะข้อมูลภายใน testThis แล้ว ซึ่งมันยังไม่มีการกำหนดค่าจึงออกมาเป็น undefined 
    ```javascript
    console.log(this)
    //Window {external: Object, chrome: Object, document: document, CustomElements: Object, _perfRefForUserTimingPolyfill: Performance…}
    function testThis() {
      console.log(this)
    }
    testThis(); //undefined
    ```
## Comparison Operators & Equality
  loadding
  
## Reference
  1. dsfsdf

## Function
  1. dsfsdf
  
# };

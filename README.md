# Javascript Basic() {

**บทความ Javascript เบื้องต้น ใช้ภาษาที่น่าจะเข้าใจกันได้ง่าย By [Heng Indy Anvil](https://www.facebook.com/LaDscaLEs)
> บทความเหมาะสำหรับผู้ที่ยังไม่มีความรู้หรือยังไม่ค่อยมีความรู้ทางด้าน Programming               โดยตั้งใจว่าจะเขียนปูพื้นไปเรื่อย ๆ ก่อน จนคิดว่าพอสมควรแล้ว จะขยับไปทางด้าน angularjs

## Table of Contents
  1. [Types](#types)
  1. [References](#references)
  1. [Check Type](#check-type)
  1. [Operators](#operators)
  1. [Function](#function)

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Types
  ชนิดของตัวแปรใน Javascript นั้น จากที่ผมได้พัฒนา Web Applicationได้เจออะไรแปลก ๆ มาพอสมควร งั้นผมจะแจกแจงที่ละตัวเลยนะครับ
  1. [string](#types) (ตัวอักษร)
    เอาไว้เก็บข้อมูลจำพวก ข้อความ, ตัวอักษร ใน Javascript นั้น การกำหนดข้อความต้องทำสัญลักษณ์เปิดและปิด ทำได้ 2 แบบ คือ
    - single quote(') ตัวอย่าง "Heng Indy Anvil", "123456", "♥"
    - double quote(") ตัวอย่าง 'Heng Indy Anvil', '123465', '♥'
  1. [number](#types) (ตัวเลข)
    เอาไว้เก็บข้อมูลจำพวก ตัวเลข ทั้งหมด ทั้งจำนวนเต็ม จำนวนจริง ตัวอย่าง
    ```javascript
    -12, 0, 125, 64.15
    ```
    
  1. [boolean](#types) (เท็จจริง)
    เอาไว้เก็บข้อมูลจำพวก ค่าเท็จจริง ตัวอย่าง
    ```javascript
    true, false
    ```
    
  1. [date](#types) (วัน)
    เอาไว้เก็บข้อมูลจำพวก วัน ตรงตัวมาก ๆ เลย ตัวอย่าง
    ```javascript
    'Fri Dec 25 2015 09:45:16 GMT+0700 (SE Asia Standard Time)'
    ```
    
  1. [array](#types) (ช่องเก็บของ)
    เอาไว้เก้บข้อมูลจำพวก ชนิดเดียวกัน แต่เก็บไว้เป็นจำนวนมาก (ให้มองเหมือนลังเบียร์ที่ข้างในมีช่องไว้ใส่ขวด) ตัวอย่าง 
    ```javascript
    [0,1,2]
    ["a","b",'c']
    ```
    
  1. [object](#types) (เลโก้)
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
    
  1. [global](#types) (window)
    หลายคนอาจจะสับสนว่าทำไมมี global มีนเป็นชื่อเรียกของตัวแปรอิสระอยู่บนสุดของพวก Class แต่ในนี้ไม่ใช่ทุกหน้า Page จะมีตัวแปร window อยู่เสมอ ๆ ซึ่ง window มีคุณสมบัติเป็น object แต่ชื่อเรียกจริง ๆ เมื่อทำงานตรวจสอบ Type จะได้เป็น Global
    ```javascript
    Window {external: Object, chrome: Object, document: document, CustomElements: Object, _perfRefForUserTimingPolyfill: Performance…}
    ```
    
  1. [function](#types) (บทบาท, การทำงาน)
    เป็นรูปแบบในการสั่งทำงาน เหมือนใบสั่งเมื่อเราประกาศว่ามีใบสั่งแบบนี้นะ แล้วเอามาใช้ ดังนั้นการทำงานในใบสั่งจึงเกิดขึ้น
    ```javascript
    function talkDate() {
      /**
       * เขียยใบสั่ง talkDate ขึ้นมา
       * โดยให้มีการทำงาน คือ แสดงค่า วันที่ปัจจุบันออกมา
       */
      console.log(new Date());
    }
    /**
     * ใช้ใบสั่ง talkDate ให้ทำงานได้
     */
    talkDate();
    ```
  
  1. [null](#types) (ค่าที่ไม่รู้)
    เป็นข้อมูลที่ไม่รู้ค่า ไม่มีใช่มีค่านะ แต่เป็นข้อมูลที่เอาไปใช้อะไรไม่ได้ ยิ่งกว่าขยะอีก(แบบใส่อารมณ์หน่อย ๆ) เหมือนการที่เรากรอกแบบฟอร์มไม่ครบ แต่คนนำใบเราไปทำสถิติแล้วดันไม่มีแต่จำเป็นต้องใส่ข้อมูลอะไรลงไปบางอย่าง ซึ่งไม่สามารถนำไปใช้อะไรได้

  1. [undefined](#types) (ไม่มีค่า)
    ตรงตัวตรง ไม่มีข้อมูล ไม่มีค่า

  1. [this](#types) (ค่า ณ จุดนั้น, ที่จริงมันก็เป็น object นี่แหละ)
    this ตรงปกติ ถ้าเป็นภาษา VB เป็น Me ซึ่งดูการใช้คำมันสื่อมาก คือ เป็นค่าของมันเอง เหมือนกับเวลาคนทั้งโลกจะกำหนดชื่อเรียกเราเป็นชื่อจริง แต่พอเข้ามาในบ้าน คนในบ้านอาจจะกำหนดชื่อเราเป็นชื่อเล่นในการเรียกใช้ก็ได้ หรือถ้าคนในบ้านไม่ได้กำหนดในการเรียก ก็ใช้ชื่อจริงนั้นแหละในการเรียกหา
    จากตัวอย่างข้างใต้จะเห็นว่า this ที่ใช้ครั้งแรก คือ ระยะข้อมูลสูงสุดของหน้า Page จึงเป็น window ออกมา พอเราสร้าง Function ขึ้นมา แล้วเรียก this ออกมา ซึ่งตามปกติ this ที่เรียกออกมานั้น คือ ระยะข้อมูลภายใน testThis แล้ว ซึ่งมันยังไม่มีการกำหนดค่าจึงออกมาเป็น undefined 
    ```javascript
    console.log(this);
    //Window {external: Object, chrome: Object, document: document, CustomElements: Object, _perfRefForUserTimingPolyfill: Performance…}
    function testThis() {
      console.log(this);
    }
    testThis(); //undefined
    ```
    
**[⬆ กลับไปด้านบน](#table-of-contents)**

## References
  การประกาศตัวแปร หลายคนที่ไม่เคยเขียนโปรแกรมมาอ่านคงไม่เข้าใจตัวแปรคืออะไร มันคือป้ายชื่อนั้นเอง! ตัวอย่าง
  ```javascript
    var company = "Heng Indy Anvil";
  ```
  
  เวลาเราเรียก company ค่าของมันก็คือ "Heng Indy Anvil" นั้นเอง 
  คราวนี้การประกาศตัวแปรมันมีทั้งหมดอยู่ 3 อย่าง ด้วยกัน คือ var, const, let ซึ่ง const กับ let มาใน ecmascript 6
  - var เป็นการประกาศแบบกึ่ง global คือ ถ้าประกาศไม่ได้อยู่ภายใต้ function จะเข้าไปอยู่ใน window แต่ถ้าประกาศภายใต้ function ก็ใช้ได้แค่ใน function
  - const เป็นการประกาศค่าคงที่ คือ ไม่สามารถเปลี่ยนค่าได้อีกแล้ว ที่เหลือก็เหมือน var 
  - let เป็นการประกาศค่าคล้าย ๆ var แต่แตกต่างตรงที่ไม่ได้มีส่วนเขี่ยวข้องใน window และ ถ้าใช้ประกาศ ใน if, for, while จะมองเป็นคนละตัวกับ var 
  ตัวอย่างข้างใต้ จะสามารถดูการไหลของข้อมูลได้ดีพอสมควรนะครับ let บาง Browser ยังไม่รองรับนะครับ อาจจะเอาไป ทดลองไม่เพื่อได้ ถ้าต้องการทดลอง[แนะนำ บทความที่2](http://plnkr.co/edit/xL2gCWFyfSvNFXyjzJoQ?p=preview)
  ```javascript
  console.log(window)     //Window {external: Object, chrome: Object, document: document, angular: Object, ng339: 3…}
  console.log(this)       //Window {external: Object, chrome: Object, document: document, angular: Object, ng339: 3…}
  window.hia = 'good';
  console.log(window.hia) //good
  
  var var1 = 'VV';
  var var2 = 'VV2';
  const con1 = 'CC';
  let let1 = 'LL';
  console.log(window.var1); //VV
  console.log(window.con1); //CC
  console.log(window.let1); //undefined
  console.log(var1);      //VV
  console.log(var2);      //VV2
  console.log(con1);      //CC
  console.log(let1);      //LL
  
  function fn() {
    var var2 = 'vvvv2';
    console.log(window);  //window
    console.log(this);    //undefined
    console.log(var1);    //VV
    console.log(var2);    //vvvv2
    console.log(con1);    //CC
    console.log(let1);    //LL
    let let2 = 'LL2';
    console.log(let2);    //LL2
  }
  fn(); 
  console.log(var2);      //VV2
  //console.log(let2);    //Error let2 is not defined ..... not work
  ```
  
  จากตัวอย่างข้างใต้นี้จะเห็นความสัมพันธ์ตัวแปรในแบบ function เป็นอย่างดี จะเห็นว่า fn1 ถึง fn9 ทำงานอย่างไม่มี error เพราะว่า sub function ข้างในนั้น ถูกกำหนดค่าเอาไว้ให้ผูกกับ v1 ซึ่งเป็นของ function นั้น ๆ แต่จะเห็นว่า fn11 ถึง fn13 ทำงานไม่สมบูรณ์ เพราะ sun function(fn12) ข้างใต้นั้นไม่ได้ถูกกำหนดไว้ภายในอย่างแท้จริงจึงไม่สามารถเรียกใช้ v1 ได้...ผมไม่รู้ศัพท์ทางการคืออะไร(-_-") แต่ผมเรียกว่า "ตัวแปรที่ไม่ตาย" เพราอะไรผมถึงกล่าวแบบนั้น มันเป็น เพราะว่า main function นั้นส่ง sub function ออกมาแล้วจะมีบางคนคิดว่า main function คงตายไปแล้ว ซึ่งความจริงมันไม่ใช่ การที่เราส่ง sub function ออกมานั้นมันจะมีการผูก main function อยู่ด้วย ดังนั้น main function จึงยังไม่ตายหายไป แต่เราจะเห็นว่า fn12 นั้น ไม่ได้เป็น sub function แท้จริง จึงไม่ได้มีการผูกกับ main function (จริง ๆ มันคือเรื่อง stack)
  ```javascript
    var testfn = null;
    
    function fn1(){
      var v1 = "variable";
      function fn2(){
        return v1;
      }
      return fn2;
    }
    testfn = fn1();  
    testfn();   //variable
    
    function fn3(){
      var v1 = "variable";
      var fn4 = function(){
        return v1;
      }
      return fn4;
    }
    testfn = fn3();  
    testfn();   //variable
    
    var fn6 = ""
    function fn5(){
      var v1 = "variable";
      fn6 = function(){
        return v1;
      }
      return fn6;
    }
    testfn = fn5();  
    testfn();   //variable
    
    var fn7 = function(){
      var v1 = "variable";
      fn8 = function(){
        return v1;
      }
      return fn8;
    }
    testfn = fn7();  
    testfn();   //variable
    
    var fn9 = function(){
      var v1 = "variable";
      var fn10 = function(){
        return v1;
      }
      return fn10;
    }
    testfn = fn9();  
    testfn();   //variable
    
    var fn12 = function(){
      return v1;
    }
    var fn11 = function(){
       var v1 = "variable";
       return fn12;
    }
    testfn = fn11();  
    testfn();   //v1 is not defined
    
    function fn13(){
       var v1 = "variable";
       return fn12;
    }
    testfn = fn13();  
    testfn();   //v1 is not defined 
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Check Type
  จากหัวข้อ Type ที่ผ่านไป ที่ทุกคนสงสัยผมรู้ชนิดมันมาได้ยังไง มันมีการตรวจสอบอยู่ 2 อย่าง เท่าที่รู้ คือ
  - typeof(....)
  - Object.prototype.toString.call(....)
  ```javascript
    console.log(typeof("Heng Indy Anvil"))  //string
    console.log(Object.prototype.toString.call("Heng Indy Anvil"))  //[Object String]
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Operators
  เรื่องนี้เป็นเกี่ยวกับเครื่องหมายนะครับ ซึ่งก็แบ่งได้อีก 4 ประเภท
  1. เครื่องหมายทางคณิตศาสตร์ ได้แก่ +(บวก), -(ลบ), *(คูณ) และ /(หาร)... โดยลำดับความสำคัญ คือ (), *, /, + และ - ตามลำดับ
  2. เครื่องหมายเพิ่มลดค่า ได้แก่ ++(เพิ่มขึ้นไป1), --(ลดลงไป1), +=3(เพิ่มขึ้นไป3), -=(ลดลงไป3)
  3. เครื่องหมายเปรียบเทียบ ได้แก่ ==(เท่ากับ), ===(เท่ากับทุกประการ), >(มากกว่า), <(น้อยหว่า), >=(มากกว่าหรือเท่ากับ), <=(น้อยกว่าหรือเท่ากับ), !=(ไม่เท่ากับ), !==(ไม่เท่ากับทุกประการ)
  4. เครื่องหมายตรรก ได้แก่ &&(และ), ||(หรือ), !(ไม่)
  ทั้งหมดที่กล่าวมา เป็นเพียงส่วนหนึ่งเท่านั้นเอง ซึ่งได้ใช้กันบ่อย ๆ อยู่แล้ว ซึ่งผู้ที่สนใจที่พึ่งจะเริ่มต้นเขียนโปรแกรม อาจจะสับสนตรงเครื่องหมายเปรียบเทียบและตรรก โดยผู้ที่มีพื้นฐานทางคณิตศาสตร์คงเข้าใจอะไรไม่ยาก มาดูตัวอย่างกันเลย
  ```javascript
    console.log(1+2);     //3  
    console.log(10-4);    //6
    console.log(2*5);     //10
    console.log(1/2);     //0.5
    console.log(1+2*3/4)  //2.5 
    console.log((1+2)*3/4)  //2.25 
    
    var v1 = 0;
    v1++;
    console.log(v1)    //1
    v1++;
    console.log(v1)    //2
    v1--;
    console.log(v1)    //1
    v1+=6;
    console.log(v1)    //7
    v1-=10;
    console.log(v1)    //-3
    
    console.log('10'==10);  //true
    console.log('1'==10);   //false
    console.log('10'===10); //false
    console.log(10===10);   //true
    console.log(5>10);      //true
    console.log(5<10);      //false
    console.log(5>=5);      //true
    console.log(5<=4);      //true
    console.log('5'!=5);    //false
    console.log(5!==5);     //true
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Function
  1. dsfsdf

**[⬆ กลับไปด้านบน](#table-of-contents)**

# };

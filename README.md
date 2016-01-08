# Javascript Basic() {

**บทความ Javascript เบื้องต้น ใช้ภาษาที่น่าจะเข้าใจกันได้ง่าย By [Heng Indy Anvil](https://www.facebook.com/LaDscaLEs)
> บทความเหมาะสำหรับผู้ที่ยังไม่มีความรู้หรือยังไม่ค่อยมีความรู้ทางด้าน Programming               โดยตั้งใจว่าจะเขียนปูพื้นไปเรื่อย ๆ ก่อน จนคิดว่าพอสมควรแล้ว จะขยับไปทางด้าน angularjs

## Table of Contents
  1. [Types](#types)
  1. [References](#references)
  1. [Check Type](#check-type)
  1. [Operators](#operators)
  1. [Condition](#condition)
  1. [Loop](#loop)
  1. [Function](#function)
  1. [Class](#class)

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
  - const เป็นการประกาศค่าคงที่ คือ ไม่สามารถเปลี่ยนค่าได้อีกแล้ว สามารถประกาศใช้ได้แค่ใน if, for, while
  - let เป็นการประกาศค่าคล้าย ๆ const แต่แตกต่างตรงที่ไม่ใช่ค่าคงที่ คือ สามารถเปลี่ยนแปลงค่าได้
  ตัวอย่างข้างใต้ จะสามารถดูการไหลของข้อมูลได้ดีพอสมควรนะครับ let บาง Browser ยังไม่รองรับนะแนะนำ ณ วันที่ (2016/01/08) คือ Browser EDGE
  ```javascript
  console.log(window);    //Window {external: Object, chrome: Object, document: document, angular: Object, ng339: 3…}
  console.log(this);      //Window {external: Object, chrome: Object, document: document, angular: Object, ng339: 3…}
  window.hia = 'good';
  console.log(window.hia); //good
  
  var var1 = 'VV';
  var var2 = 'VV2';
  const con1 = 'CC';
  let let1 = 'LL';
  console.log(window.var1); //VV
  console.log(window.var2); //VV2
  console.log(window.con1); //undefined
  console.log(window.let1); //undefined
  console.log(var1);      //VV
  console.log(var2);      //VV2
  console.log(con1);      //Error con1 is not defined ..... not work
  console.log(let1);      //Error let1 is not defined ..... not work
  
  if (1==1) {
    let let1 = 'llll';
    console.log(let1);    //llll
  }
  console.log(let1);      //Error let1 is not defined ..... not work
  
  for(let let1=0;let1<2;let1++){
    console.log(let1);    
  }   //results per cycle : 0 1
  
  for(let let1=0;let1<2;let1++){
    let let1 = 99;
    console.log(let1);    
  }   //results per cycle : 99 99
  
  function fn() {
    var var2 = 'vvvv2';
    const con1 = 'cccc';
    let let1 = 'llllll';
    console.log(window);  //window
    console.log(this);    //window
    console.log(var1);    //VV
    console.log(var2);    //vvvv2
    console.log(con1);    //cccc
    console.log(let1);    //llllll
  }
  fn(); 
  
  console.log(var2);      //VV2
  console.log(let1);      //Error let1 is not defined ..... not work
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
    console.log(typeof("Heng Indy Anvil")); //string
    console.log(Object.prototype.toString.call("Heng Indy Anvil")); //[Object String]
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Operators
  เรื่องนี้เป็นเกี่ยวกับเครื่องหมายนะครับ ซึ่งก็แบ่งได้อีก 4 ประเภท
  1. เครื่องหมายทางคณิตศาสตร์ ได้แก่ +(บวก), -(ลบ), *(คูณ) และ /(หาร)... โดยลำดับความสำคัญ คือ (), *, /, + และ - ตามลำดับ
  2. เครื่องหมายเพิ่มลดค่า ได้แก่ ++(เพิ่มขึ้นไป1), --(ลดลงไป1), +=3(เพิ่มขึ้นไป3), -=(ลดลงไป3)
  3. เครื่องหมายเปรียบเทียบ ได้แก่ ==(เท่ากับ), ===(เท่ากับทุกประการ), >(มากกว่า), <(น้อยกว่า), >=(มากกว่าหรือเท่ากับ), <=(น้อยกว่าหรือเท่ากับ), !=(ไม่เท่ากับ), !==(ไม่เท่ากับทุกประการ)
  4. เครื่องหมายตรรก ได้แก่ &&(และ), ||(หรือ), !(ไม่)... ในหัวข้อ 4 นี้ต้องทำความเข้าใจหน่อยนะครับ คือ คำว่าและให้มองเป็นตัวคูณ, คำว่าหรือให้มองเป็นตัวบวก, คำว่าไม่ให้คิดเป็นตรงข้าม, trueให้มองเป็น1, falseให้มิงเป็น0 ตัวอย่าง
  
      1. 1*1 คิดเป็น 1
      2. 1*0 คิดเป็น 0
      3. 0*0 คิดเป็น 0 (จาก1-3 ทำการคิดได้ว่าถ้ามี 0(false) เพียงตัวเดียว จะออกมาเป็น 0(false)
      4. 1+1 คิดเป็น 1
      5. 1+0 คิดเป็น 1
      6. 0+0 คิดเป็น 0 (จาก4-6 ทำการคิดได้ว่าถ้ามี 1(true) เพียงตัวเดียว จะออกมาเป็น 1(true)
      7. !0  คิดเป็น 1
      8. !1  คิดเป็น 0 (จาก7-8 ทำการคิดได้ว่าถ้ามี !(ตรงข้าม) ให้สลับจาก 1เป็น0, 0เป็น1
      
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
    console.log(v1);  //1
    v1++;
    console.log(v1);  //2
    v1--;
    console.log(v1);  //1
    v1+=6;
    console.log(v1);  //7
    v1-=10;
    console.log(v1);  //-3
    
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
    
    console.log(true && true);    //true
    console.log(true && false);   //false
    console.log(false && false);  //false
    console.log(true || true);    //true
    console.log(true || false);   //true
    console.log(false || false);  //false
    console.log(!true);           //false
    console.log(!false);          //true
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Condition
  ในหัวข้อนี้คือเงื่อนไข ซึ่งเราเคยชินกับเรื่องพวกนี้อยู่แล้ว เพราะ ชีวิตทั้งวันเรามีเงื่อนไขในเส้นทางอยู่เสมอ เช่น เลือกกินข้าวหรือก๋วยเตี๋ยว, ต้องเป็นตุ๊กตาหมีสีน้ำตาลเท่านั้น จะเห็นว่าที่ยกมานั้นเป็นเงื่อนไขในการกระทำบางอย่าง โดยในคำว่าเงื่อนไขในการเขียนโปรแกรมนั้นใช้คำว่า if ซึ่งแปลว่าถ้า
  และมีคำว่า else ซึ่งแปลว่าไม่เช่นนั้น(มีตัวเพิ่มขึ้นมาให้คิดเพิ่มอีกซะงั้น) ซึ่ง else เป็นตัวที่กระทำก็เมื่อต่อไม่อยู่ในเงื่อนไขที่กำหนดไว้ เช่น ถ้าเงินเดือน 15,000 บาท ผมจะรับคุณเข้าทำงานไม่เช่นนั้นคุณก็ออกไป จะเห็นว่าเมื่อไม่เข้าเงื่อนไขก็ยังสามารถมีการกระทำต่อได้อยู่
  ยังไม่หมดกีอกแค่นี้ ในเงื่อนไข มักมีตัวสำรองเสมอ ยังไงนะหรอ เช่น ถ้าวันนี้เป็นวันจันทร์ จะใส่เสื้อสีเหลือง ไม่เช่นนั้นถ้าวันนี้เป็นวันอังคาร จะใส่เสื้อสีชมพู ไม่เช่นนั้น จะเสื้อสีขาว จะเห็นว่ามีลำดับการคิดเป็นขั้นตอนซับซ้อนเพิ่มขึ้นมาอีก 1 ขั้น 
  การบรรยายข้างต้นโดยภาษาทั่วไปนั้นน่าจะมองให้เห็นภาพกันได้บางแล้ว เดี๋ยวเรามาดูตัวอย่างข้างใต้กันเลยว่า ในการเขียนโปรแกรม รูปแบบภาษานั้น จะมีการเขียนแบบไหนบ้างซึ่งก็ไม่มากไม่น้อย พอจะเอามาประยุกต์ได้
  ```javascript
    if (1===1) {
      console.log(1); //working
    }
    
    if (1===2){
      console.log(1);
    } else {
      console.log(2); //working
    }
    
    if (1===2){
      console.log(1);
    } else if (1===1) {
      console.log(2); //working
    } else {
      console.log(3); 
    }
    
    if (1===2){
      console.log(1);
    } else {
      console.log(2); //working
      if (1===1){
        console.log(3); //working
      } else {
        console.log(4);
      }
    }
    
    if (1===2){
      console.log(1);
    } else {
      console.log(2); //working
      if (1===1){
        console.log(3); //working
      }
      if (2===2){
        console.log(4); //working
      }
    }
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Loop
  การทำงานซ้ำ(วน) เป็นการทำงานที่เราคุ้นเคยดียกตัวอย่างง่ายมาก เราจะมีชีวิตไปเรื่อยๆจนกว่าจะตาย(-_-") โดยในหว่างมีชีวิตเราจะ..(กำหนดเอาเอง จะทำอะไรก็ได้).. จะเห็นว่ามีจะมีการทำงานโดยมีเงื่อนไขเป็นตัวกำหนดถ้าตรงกับความเป็นจริงตามเงื่อนไขก็ยังต้องทำงานซ้ำๆต่อไป
  โดยการเขียนวน จะมีลักษณะอยู่หลายอย่าง
  1. do...while จะทำงานก่อน แล้วค่อยไปดูเงื่อนไข ถ้ายังตรงตามเงื่อนไขก็จะทำงานซ้ำ
  2. while...do จะดูเงื่อนไขก่อน แล้วค่อยทำงาน เมื่อทำงานเสร็จจะมาดูเงื่อนไขอีกทีถ้า ไม่ตรงตามเงื่อนไขแล้ว จะไปทำงานลำดับต่อไป
  3. for...loop อันนี้จะพิเศษหน่อย ต้องทำความเข้าใจ โดยการทำงานจะมีอยู่ 4 ช่วง 
      1. กำหนดค่าเริ่มต้น
      2. เงื่อนไข
      3. จบรอบ
      4. การทำงานภายในรอบ
    ซึ่งการทำงานการเป็นลำดับตามนี้ 1-->2-->4-->3-->2-->4-->3 ซึ่งจามเห็นว่า 1 จะทำงานรอบเดียวคือครั้งแรก ต่อมาจะเป็น 2 คือตรวจสอบเงื่อนไขก่อนว่าเป็นจริงไหม ต่อมาจะเป็น 4 จะทำงานภายในวนที่กำหนดไว้ ต่อมาจะเป็น 3 จบ 1 รอบก็จะมาทำต่อนี้ 1 ครั้ง และก็จะไปทำ 2 อีกครั้ง ตามลำดับไปเรื่อย ๆ จนกว่า เมื่อถึง 2 แล้วเงื่อนไขตรวจสอบว่าไม่จริงตามที่กำหนดไว้ก็จะไม่ไปทำงาน 4 กับ 3 แล้ว จะไปทำงานในลำดับอื่นต่อไป
  โดย 3 อย่างนี้ เป็นส่วนหนึ่งในรูปแบบการทำงานซ้ำเท่านั้น แต่แค่นี้ก็เพียงพอต่อการเขียนโปรแกรมแล้ว เราจะมาดูตัวอย่างข้างใต้เลยดีกว่า ว่ารูปแบบการเขียนโปรแกรม javascript จะเป็นแบบไหน
  ```javascript
    var l1 = 0;
    do {
      console.log(l1);
      l1++;
    }
    while (l1 < 10); //results per cycle : 0 1 2 3 4 5 6 7 8 9
    console.log(l1);  //10
    
    l1 = 0;
    do {
      l1++;
      console.log(l1);
    }
    while (l1 < 10); //results per cycle : 1 2 3 4 5 6 7 8 9 10
    console.log(l1);  //10
    
    l1 = 0;
    while (l1 < 10) {
      console.log(l1);
      l1++;
    } //results per cycle : 0 1 2 3 4 5 6 7 8 9
    console.log(l1);  //10
    
    l1 = 0;
    while (l1 < 10) {
      l1++;
      console.log(l1);
    } //results per cycle : 1 2 3 4 5 6 7 8 9 10
    console.log(l1);  //10
    
    for (l1=0; l1<10; l1++) {
      console.log(l1);
    } //results per cycle : 0 1 2 3 4 5 6 7 8 9
    console.log(l1);  //10
  ```

**[⬆ กลับไปด้านบน](#table-of-contents)**

## Function
  มาถึงเรื่องนี้แล้วเป็นเรื่องที่ดีมากเลยทีเดียวประโยชน์ของมันมีความหลากลายมาก ทั้งลดความซ้ำซ้อนของการเขียนและทำให้อ่านการเขียนโปรแกรมง่ายขึ้นด้วย function นี้ถ้าให้มองแบบง่าย ๆ ก็ คือ ใบสั่งทำงานนั้นเอง เช่น เราซื้อกล่องประกอบหุ่นยนต์กากๆมา 1 อัน ในนั้นจะมีคู่มือมาให้เป็นขั้นตอนทำประกอบ คู่มือใบเล็ก ๆ นั้นแหละครับคือใบสั่ง ส่วนขั้นตอนก็คือการทำงานนั้นเอง โดยใบสั่งนี้สามารถใช้ได้หลายครั้งไม่จำกัดเลยก็ว่าได้
  ประโยชน์ที่ผมเห็นของ function ที่เคยเกริ่นไว้ก่อนหน้านี้ คือ 2 อย่าง ดังนี้
  1. อ่านการทำงานของโปรแกรมได้ง่าย อันนั้นเหมาะแก่การเมื่อเวลาผ่านไปนาน แล้วเรากลับมาอ่านการทำงานใหม่จะสามารถเข้าใจอะไรได้ง่าย อาทิ ใน 1 งานของการหาค่าพื้นที่ 4 เหลี่ยม เรามี 3 ใบสั่ง คือ ใบสั่งรับค่า, ใบสั่งคำนวณค่า และ ใบสั่งแสดงผลของค่า จะเห็นว่ามันเป็นสัดส่วนอ่านเข้าใจได้ง่าย แล้วในใบสั่งจะทำงานอะไรก็ทำไปให้เข้ากับชื่อที่ได้ตั้งไว้ แต่ถ้าเราไม่ใช้ใบสั่งละ มันก็จะเป็นแบบนี้ รับค่ากว้าง,รับค่ายาว,นำค่ากว้างและค่ายาวมาคูณกันนำไปเก็บไว้ในกระดาษทด,นำกระดาษทดสอบขึ้นมาเขียนค่าตามกระดาษทดใส่ในกระดาษทดสอบ จะเห็นว่ามันยาวจนบางทีมันต้องอ่านทุกตัวถึงจะเข้าใจการทำงาน  ซึ่งมันลำบากไป จัดเห็นหมวดหมู่ใบสั่งแล้วถ้าเราอยากรู้ลึกของอะไรค่อยเข้าไปดูทำความเข้าใจจะดีกว่า
  2. ลดความซ้ำซ้อนของโปรแกรม อันนี้เหมาะกับการทำงานอะไรที่ซ้ำๆซากๆแล้วยังต้องเขียนยาวๆยืดๆอยู่ตลอดทั้งทีการเขียนมันเหมือนกันหมดเลย ยกตัวอย่างเช่น ถ้าเราต้องการแสดงผลข้อมูล 3 รอบ โดยเราต้องเขียน นำกระดาษทดสอบขึ้นมาเขียนค่าตามกระดาษทดใส่ในกระดาษทดสอบ, นำกระดาษทดสอบขึ้นมาเขียนค่าตามกระดาษทดใส่ในกระดาษทดสอบ, นำกระดาษทดสอบขึ้นมาเขียนค่าตามกระดาษทดใส่ในกระดาษทดสอบ ซึ่งจะเห็นว่ามันดูยาวและไม่เหมาะกับการอ่านเลย แต่ถ้าเราเปลี่ยนมาเป็น ใบสั่งแสดงผลค่า, ใบสั่งแสดงผลค่า, ใบสั่งแสดงผลค่า จะเห็นว่าเรามันสั้นลงและทำความเข้าใจได้ง่ายขึ้นด้วย ซึ่งเมื่อเราเขียนโปรแกรมจริง ๆ จะเห็นว่าความยาว 100 บรรทัด อาจจะถูกทำความเข้าใจได้ง่ายเหลือเพียง 10 บรรทัดเท่านั้นเอง 
  จากตัวอย่างข้างใต้เราจะเห็นว่า เรานำคำสั่งไปใส่ไว้ใน function ทำให้เรารู้สึกว่าเขียนแบบธรรมดาสั้นกว่านั้นเป็นสิ่งที่ถูกต้องแล้ว เพราะ บางคำสั่งไม่จำเป็นต้องลงไปใน function หมดก้ได้ อาจจะต้องทำให้เขียนมากขึ้นกว่าเดิม แต่อย่าลืมนะครับ ถ้าเวลาผ่านไปกลับมาอ่านเพียงชื่อ function ก็ทำความเข้าใจได้เลย เพราะ ชื่อนั้นเป็นรูปแบบสื่อความหมายอยู่แล้ว
  ```javascript
    var width = null;
    var height = null;
    var success = null;
    
    //format 1
    width = 5;
    height = 10;
    success = width*height;
    console.log(success); //50
    
    //format 2
    function setValue() {
      width = 5
      height = 10;
    }
    function calculatorValue() {
      success = width*height;
    }
    function showSuccess() {
      console.log(success);
    }
    
    setValue();
    calculatorValue();
    showSuccess();  //50
  ```
  ตอนนี้เราจะมีรู้เรื่องรู้ function ลงไปอีกหน่อยคือ parameter นั้นเป็นตัวรับค่าเข้า function ความสำคัญของมันคือถ้าหากค่าที่เราต้องการใช้ใน function ต้องเป็นค่าที่ส่งมาเท่านั้น เหมือนตัวอย่างข้างบน ใน function มันตายตัวเห็นมั้ยครับ เดี๋ยวดูตัวอย่างข้างใต้นี้ คุณจะเห็นความเปลี่ยนแปลงแบบที่คุณคิดว่า ใช้ function เถอะ (ในที่นี้ผมเขียนให้ function มันยืดหยุ่นด้วยทำให้อาจจะต้องใช้ 2 function
  ```javascript
    var width = null;
    var height = null;
    var success = null;
    
    //format 1
    width = 5;
    height = 10;
    success = width*height;
    console.log(success); //50
    
    width = 15;
    height = 10;
    success = width*height;
    console.log(success); //150
    
    //format 2
    function calculatorValue(pintWidth, pintHeight) {
      return pintWidth*pintHeight;
    }
    function showSuccess(pintSuccess) {
      console.log(pintSuccess);
    }
    
    showSuccess( calculatorValue(5, 10) ); //50
    //OR
    success = calculatorValue(5, 10);
    showSuccess(success); //150
    
    showSuccess( calculatorValue(15, 10) ); //150
  ```
  จะเห็นความสามารถและประโยชน์ของ function บางส่วนไปแล้ว ซึ่งมันก็ยังไม่หมดหรอกนะครับ อันนี้แบบเด็ก ๆ เลย ซึ่ง เดี๋ยวผมจะค่อยลงลึกอีกที ในส่วนนี้ต้องการอธิบายว่า function มันทำให้ชีวิตเราง่ายขึ้นยังไง และทำให้เข้าใจง่ายขึ้น เขียนสั้นลงด้วย
  
**[⬆ กลับไปด้านบน](#table-of-contents)**

## Class
  ติดตามต่อไปนะครับ ^^ ขะแต่งงานแล้ว ขอพักสมองก่อน ไว้เจอหลัง ประมาณวันที่ 10/01/2016

**[⬆ กลับไปด้านบน](#table-of-contents)**

# };

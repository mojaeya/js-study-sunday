# π λ°°μ΄μ λ©μλ
  ### πμμ  λ©μλ
  μλ³Έ λ°°μ΄μ λ°λ‘ μμ νλ λ©μλ
  
  __1. push λ©μλ__ : λ°°μ΄ λ§μ§λ§μ νλ μ΄μμ μμλ₯Ό μΆκ°ν λ€μ κ·Έ λ°°μ΄μ κΈΈμ΄λ₯Ό λ°ν       
```javascript
var a = ["A", "B", "C"];
a.push("D"); // aμ λ΄μ© : ["A", "B", "C", "D"] : λ°νκ° = 4
``` 
   
   __2. pop λ©μλ__ : λ°°μ΄μ λ§μ§λ§ μμλ₯Ό μλΌλ΄μ΄ λ°ν
      
   ```javascript
     var a = ["A", "B", "C"];
     a.pop(); // aμ λ΄μ© : ["A", "B"] : λ°νκ° = "C"
   ```
   
   __3. shift λ©μλ__ : λ°°μ΄μ μ²« λ²μ§Έ μμλ₯Ό μ κ±°ν ν λͺ¨λ  λ°°μ΄ μμλ₯Ό μΌμͺ½μΌλ‘ μ΄λμν΄. λ°νκ°μ μ­μ λ μμμ κ°
     
   ```javascript
     var a = ["A", "B", "C"];
     a.shift(); // a  β ["B", "C"] : λ°νκ° = "A" 
   ```
      
   __4. unshift λ©μλ__ : λ°°μ΄ μλΆλΆμ μμλ₯Ό ν κ° μ΄μ μΆκ°ν ν λͺ¨λ  λ°°μ΄ μμλ₯Ό μ€λ₯Έμͺ½μΌλ‘ μ΄λμν΄(shiftμλ λ°λ λ°©ν₯).λ°νκ°μ κ·Έ λ°°μ΄μ κΈΈμ΄
   
   ```javascript
     var a = ["A", "B", "C"];
     a.unshift("X"); // a  β ["X", "A", "B", "C"] : λ°νκ° = "4" 
   ```
      
   __5. splice λ©μλ__ : νΉμ  μΈλ±μ€μ λ°°μ΄ μμλ₯Ό κ°μ λΌμΈ λ μ¬μ©νλ λ²μ© λ©μλ. μμλ₯Ό λΌμ λ£κΈ°λ§ ν  μλ μκ³  μ­μ λ§ ν  μλ μμ. μ­μ λ μμλ λ°°μ΄λ‘ λ§λ€μ΄μ λ°ν.


      * μ²« λ²μ§Έ μΈμ : λ°°μ΄μ μμ νκΈ° μμν  μμΉλ₯Ό κ°λ¦¬ν€λ μΈλ±μ€. μ΄ κ°μ΄ λ°°μ΄ κΈΈμ΄λ³΄λ€ ν¬λ©΄ λ°°μ΄ λ§μ§λ§μ μμ μμΉλ‘ κ°μ£Όνλ€. 
                   
          μ΄ κ°μ΄ μμλ©΄ μ΄ κ°μ λ°°μ΄ κΈΈμ΄λ₯Ό λν κ°μ μμ μμΉλ‘ κ°μ£Όνλ€.
      
      * λ λ²μ§Έ μΈμ : λ°°μ΄μμ μ­μ ν  μμμ κ°μ. 0μ λκΈ°λ©΄ μ΄λ ν μμλ μ­μ νμ§ μλλ€.
      
        μ΄λλ μΈμλ‘ μλ‘μ΄ μμλ₯Ό μ μ΄λ ν κ°λ λκ²¨μΌ νλ€. μλ¬΄λ° κ°λ λκΈ°μ§ μμΌλ©΄ index μ΄νμ λͺ¨λ  λ°°μ΄ μμλ₯Ό μ­μ νλ€.
    
      * μΈ λ²μ§Έ μ΄νμ μΈμ : λ°°μ΄μ μ½μν  μμμ κ°μ μΌνλ‘ κ΅¬λΆν΄μ λκΈ΄λ€. 
       
        κ°μ΄ μμΌλ©΄ λ¨μν λ°°μ΄μμ μμλ₯Ό μ­μ νλ€. 
        
   ```javascript
     var a = ["A", "B", "C", "D"];
     a.splice(2); // a  β ["A", "B"] : λ°νκ° = ["C", "D"] 
   ```  
      
      
   ```javascript
     var a = ["A", "B", "C", "D"];
     a.splice(-1); // a  β ["A", "B", "C"] : λ°νκ° = ["D"] 
   ```  
      
      
   ```javascript
     var a = ["A", "B", "C", "D"];
     a.splice(1,0,"X","Y"); // a  β ["A", "X", "Y", "B", "C", "D"] : λ°νκ° = [] 
   ``` 
      
   __7. sort λ©μλ__ : λ°°μ΄ μμ μμλ₯Ό μ λ ¬. μΈμλ‘λ μ€μ λ‘ λΉκ΅λ₯Ό λ΄λΉνλ ν¨μμ μ°Έμ‘°λ₯Ό λκΈ°λ©° λ°νκ°μ μ λ ¬λ λ°°μ΄μ.
    
   ```javascript
     var a = [5, 2, 7, 1, 3, 9, 8];
     a.sort(function(a,b) {return a - b; }); // a  β [1, 2, 3, 5, 7, 8, 9] 
   ```  
            f(a, b) < 0μ΄λ©΄ aλ₯Ό bλ³΄λ€ μμ μΈλ±μ€λ‘ μ λ ¬
            f(a, b) == 0μ΄λ©΄ aμ bμ μμλ₯Ό λ°κΎΈμ§ μμ
            f(a, b) > 0μ΄λ©΄ bλ₯Ό aλ³΄λ€ μμ μΈλ±μ€λ‘ μ λ ¬
    
  ### π μ κ·Όμ λ©μλ
    λ°°μ΄μ λ€λ₯Έ λͺ¨μ΅μΌλ‘ κ°κ³΅ν μλ‘μ΄ λ°°μ΄μ λ°ννλ©° μλ λ°°μ΄μ μμ νμ§ μμ.
  __1. join λ©μλ__ : λ°°μ΄μ λͺ¨λ  μμ κ°μ λ¬Έμμ΄λ‘ λ°κΎΌ νμ μΈμλ‘ λ°μ λ¬Έμλ‘ μ°κ²°ν΄μ λ°ν. μμ κ°μ΄ undefinedλ nullμΌ λλ κ·Έ μμ κ°μ λΉ λ¬Έμλ‘ κ°μ£Ό. 
  
  μΈμλ₯Ό μ§μ νμ§ μμΌλ©΄ μΌνλ‘ λ°°μ΄μ μμ κ°μ μ°κ²°ν΄μ λ°ν.
    
   ```javascript
     var a = ["A", "B", "C"];
     a.join("-"); // β "A-B-C" 
     a.join("");  // β "ABC"
   ```  
  
  __2. contact λ©μλ__ : μΈμλ‘ λ°μ κ°μ κ·Έ λ°°μ΄μ μμλ‘ μΆκ°ν΄μ μλ‘μ΄ λ°°μ΄μ μμ±. λ°μ μΈμκ° λ°°μ΄μ΄λ©΄ νΌμΉ νμ λ°°μ΄μ μΆκ°ν¨.  
  
  μΈμλ₯Ό μ§μ νμ§ μμΌλ©΄ μΌνλ‘ λ°°μ΄μ μμ κ°μ μ°κ²°ν΄μ λ°ν.
    
   ```javascript
     var a = ["A", "B", "C"];
     a.contact(["D", "E"]); // β ["A", "B", "C", "D", "E"]
     a.contact(["D", "E"], ["F", "G"]); // β ["A", "B", "C", "D", "E", "F", "G"]
     a.contact(1, "X", true); // β ["A", "B", "C", 1, "X", true]
     a.contact(["D", ["E", ["F", "G"]]); // β ["A", "B", "C", "D", "E", ["F", "G"]]
   ```  
   
   
  __3. slice λ©μλ__ : λ°°μ΄μ μΌλΆ μμλ₯Ό μ κ±°ν μλ‘μ΄ λ°°μ΄μ λ°ν. 
      * μ²« λ²μ§Έ μΈμ : μμλ₯Ό κΊΌλΌ μμ μμΉλ₯Ό λ»νλ μΈλ±μ€. μ΄ κ°μ΄ μμλ©΄ μ΄ μμ λ°°μ΄ κΈΈμ΄λ₯Ό λν κ°μ μμ μμΉλ‘ κ°μ£Όνλ€. μλ΅νλ©΄ 0μΌλ‘ κ°μ£Ό.
      * λ λ²μ§Έ μΈμ : μμλ₯Ό κΊΌλΌ λ§μ§λ§ μμΉλ₯Ό λ»νλ μΈλ±μ€. κ°λ¦¬ν€λ μμ λ°λ‘ μ΄μ  μμκΉμ§ μλΌλ. μ΄ κ°μ΄ μμλ©΄ λ°°μ΄ κΈΈμ΄λ₯Ό λν κ°μ λ§μ§λ§ μμΉλ‘ κ°μ£Όνλ€. μλ΅νλ©΄ λ°°μ΄μ λμΌλ‘ κ°μ£Ό.
    
   ```javascript
     var a = ["A", "B", "C", "D", "E"];
     a.slice(1, 3); // β ["B", "C"]
     a.slice(3);  // β ["D", "E"]
     a.slice(1, -1);  // β ["B", "C", "D"]
     a.slice(-3, -2);  // β ["C"]
   ```  
  
  __4. indexOfμ lastIndexOF λ©μλ__ : λ°°μ΄ μμμ μΈμλ‘ μ§μ ν κ°μ κ²μν΄μ κ°μ₯ λ¨Όμ  μ°Ύμ μμμ μΈλ±μ€λ₯Ό λ°ν. μ°Ύμ§ λͺ»νμ λλ -1μ λ°ν. 
  
  indexOfλ©μλλ μΈλ±μ€κ° μμ μͺ½λΆν° μμλλ‘ κ²μνκ³  lastIndexOfλ©μλλ μΈλμ€κ° ν° μͺ½λΆν° μ­μμΌλ‘ κ²μ.
      
      * μ²« λ²μ§Έ μΈμ : κ²μν  κ°
      * λ λ²μ§Έ μΈμ : κ²μμ μμν  μΈλ±μ€. μλ΅νλ©΄ 0μΌλ‘ κ°μ£Ό. λ°°μ΄ κΈΈμ΄λ₯Ό λλ κ°μ μλ ₯νλ©΄ κ²μνμ§ μλλ€. κ°μ΄ μμλ©΄ κ°μ λ°°μ΄ κΈΈμ΄λ₯Ό λν κ°μ μμ μμΉλ‘ κ°λ.
      
   ```javascript
     var a = ["A", "B", "C", "C", "D"];
     a.indexOf("C"); // β 2
     a.lastIndexOf("C");  // β 3
     a.indexOf("C", 3);  // β 3
   ```  
  
  __5. toStringκ³Ό toLocaleString λ©μλ__ : λ°°μ΄μ μμλ₯Ό λ¬Έμμ΄λ‘ λ°ννμ¬ μΌνλ‘ μ°κ²°ν λ­γ΄μμ΄μ λ°ν. Object.prototypeμ μλ κ°μ μ΄λ¦μ λ©μλλ₯Ό λ€μ μ μν κ². 
  
  toLocaleString λ©μλλ ν΄λΉ μ§μ­μ λ§λ μΈμ΄λ‘ λ²μ­ν λ¬Έμμ΄λ‘ λ³ν.
  
   ```javascript
     ["A", "B", "C", date].toString();  // β "A, B, C"
     [1, 2, 3, date].toString();  // β "1, ,2, 3"
     [1,[2, 3], date].toString();  // β "1, ,2, 3"
        
     var date = new Date();
     console.log(["A", "B", "C", date].toString());  // β "A, B, C, Wed Jan 03 2018 22:56:54 GMT+0900 (KST)"
     console.log(["A", "B", "C", date].toLocaleString());  // β "A, B, C, 2018. 1. 3. μ€ν 10:56:54"
   ```  
  
  ### π λ°λ³΅ λ©μλ
   λ°°μ΄μ λͺ¨λ  μμλ₯Ό μλΈννλ©° νΉμ ν μμμ μνΉνκ±°λ νΉμ  μ‘°κ±΄μ λ§μ‘±νλ μμλ₯Ό κ°μ Έμ¬ λ μ¬μ©νλ λ©μλ. λλΆλΆ μ²« λ²μ§Έ μΈμλ‘ ν¨μμ μ°Έμ‘°λ₯Ό λ°λ κ³ μ°¨ ν¨μ. μ νμ μΈ ν¨μν νλ‘κ·Έλλ°μ ννλ₯Ό λ°.
   * λ°λ³΅ λ©μλμ μΈμλ‘ μ λ¬ν ν¨μλ λ°°μ΄μ μμλ§λ€ νΈμΆλ¨. μ΄λ λ°λ³΅νλ λ°°μ΄μ΄ ν¬μλ°°μ΄μ΄λ©΄ μλ μμμ λν΄μλ νΈμΆλμ§ μμ.
   * λ°λ³΅ ν¨μ λλΆλΆμ μ²« λ²μ¬ μΈμλ‘ ν¨μλ₯Ό λ°μΌλ©° μ΄ ν¨μμλ λ€μ μΈμ μΈ κ°κ° μ λ¬λ¨. μΈμ μΈ κ° μ€μμ μ²« λ²μ§Έ μΈμλ§ μ¬μ©νλ κ²½μ°κ° λ§μΌλ©°, κ·Έλ° κ²½μ°μλ λ λ²μ§Έ μΈμμ μΈ λ²μ§Έ μΈμλ₯Ό μλ΅ν  μ μμ.
     - μ²« λ²μ§Έ μΈμ(value) : νμ¬ μ²λ¦¬νκ³  μλ© λ°°μ΄ μμμ κ°
     - λ λ²μ§Έ μΈμ(index) : νμ¬ μ²λ¦¬νκ³  μλ λ°°μ΄ μμμ μΈλ±μ€
     - μΈ λ²μ§Έ μΈμ(array) : λ©μλκ° μ μ©λλ λ°°μ΄μ μ°Έμ‘°
   * reduceμ reduceRightλ₯Ό μ μΈν λλ¨Έμ§ λ°λ³΅ λ©μλμλ λ λ²μ§Έ μΈμλ₯Ό μ§μ ν  μ μλ€. λ λ²μ§Έ μΈμλ μ²« λ²μ§Έ μΈμλ‘ λ°μ ν¨μ μμ this κ°μ΄λ©° μλ΅ κ°λ₯.

 __1. forEach λ©μλ__ : μΈμλ‘ λ°μ ν¨μλ₯Ό λ°°μ΄μ μμλ³λ‘ ν λ²μ© μ€ν. κ·Έ ν¨μμλ μΈμ μΈ κ°(value, index, array)κ° μ λ¬λ¨.
 
   ```javascript
     var a = [1, 2, 3, 4, 5];
        
     // λ°°μ΄μ ν©μ κ΅¬νλ€
     var sum = 0;
     a.forEach(function(value) { sum += value; });
     console.log(sum);  // 15 
        
     //κ° λ°°μ΄ μμμ μ κ³±μ κ΅¬νλ€
     a.forEach(function(v,i,a) { a[i] = v*v; });
     console.log(a);   // [1, 4, 9, 16, 25]
   ```
 
 
 __2. map λ©μλ__ : μΈμλ‘ λ°μ ν¨μλ₯Ό λ°°μ΄μ μμλ³λ‘ ν λ²μ© μ€ννλ©° λ§μ§λ§μλ κ·Έ ν¨μκ° λ°νν κ°μΌλ‘ μλ‘μ΄ λ°°μ΄μ μμ±. mapμ μΈμλ‘ λκΈ°λ ν¨μλ λ°λμ κ°μ λ°νν΄μΌν¨
 
   ```javascript
    var a = [1, 2, 3, 4, 5];
    var b = a.map(function(x) { return 2*x; });  // b = [2, 4, 6, 8, 10]
   ```
   
 __3. reduce λ©μλ__ : λ°°μ΄μ μ²« λ²μ§Έ μμλΆν° λ§μ§λ§ μμκΉμ§μ ν©μ± κ³± μ²λ¦¬λ₯Όνλ€. ν©μ± κ³± μ²λ¦¬λ λ°°μ΄ μμ νλλ₯Ό ν¨μλ‘ μ²λ¦¬ν νμ κ·Έ λ°νκ°μ λ€μ λ² μμλ₯Ό μ²λ¦¬ν  λ ν¨μμ μλ ₯ κ°μΌλ‘ μ¬μ©νλ μ²λ¦¬ λ°©λ². 
 μλ―Έκ° μμλ₯Ό μ²λ¦¬ν ν¨μκ° κ°μ λ°νν¨.
 
 ```javascript
 var a = [1, 2, 3, 4, 5];
 a.reduce(function(prev, value) { return prev + value; }, 0);  // 15
 a.reduce(function(prev, value) { return prev + value; });  // 15
 ```

# π λ€μ°¨μ λ°°μ΄
  μλ°μ€ν¬λ¦½νΈλ λ€μ°¨μ λ°°μ΄μ μ μνκΈ° μν λ¬Έλ²μ μ κ³΅νμ§ μμ§λ§, λ°°μ΄μ λ°°μ΄μ μ€μ²©νλ©΄ λ€μ°¨μ λ°°μ΄κ³Ό λΉμ·ν κΈ°λ₯μ κ΅¬νν  μ μμ.
  
  ### π 2μ°¨μ λ°°μ΄μ μμ±
   ```javascript
    // 2μ°¨μ λ°°μ΄μ μμ±
    var x= new Array(3);  // μ°λ³μ λ°°μ΄ λ¦¬ν°λ΄ []λ‘ νκΈ°ν  μλ μμ
    for(var i=0; i<3; i++) {
      x[i] = new Array(3);
    }
    
    // 2μ°¨μ λ°°μ΄μ κ°μ λμ
    for(var count=1, i=0; i<3; i++) {
      for(var j=0; j<3; j++) {
        x[i][j] = count++;
       }
     }
   ```
  ### π λ€μ°¨μ λ°°μ΄μ μμ±
   2μ°¨μ λ°°μ΄κ³Ό κ°μ λ°©λ²μΌλ‘ λ€μ°¨μ λ°°μ΄ λ§λ€ μ μμ.
   
   ```javascript
    // 3μ°¨μ λ°°μ΄μ μμ±
    var x= new Array(3);  // μ°λ³μ λ°°μ΄ λ¦¬ν°λ΄ []λ‘ νκΈ°ν  μλ μμ
    for(var i=0; i<3; i++) {
      x[i] = new Array(3);
      for(var j=0; j<3; j++) {
        x[i][j] = new Array(3);
      }
    }
    
    // 3μ°¨μ λ°°μ΄μ κ°μ λμ
    for(var count=1, i=0; i<3; i++) {
      for(var j=0; j<3; j++) {
        x[i][j] = count++;
       }
     }
   ```
# π μ μ¬ λ°°μ΄ κ°μ²΄
  μλ°μ€ν¬λ¦½νΈ νλ‘κ·Έλ¨μμλ λ°°μ΄μ μλμ§λ§ λ°°μ΄λ‘ μ²λ¦¬ν  μ μλ κ°μ²΄(μ μ¬ λ°°μ΄ κ°μ²΄)λ₯Ό λ€μν μν©μμ μ¬μ©ν¨. 
  ### Array.prototypeμ λ©μλλ₯Ό μ μ¬ λ°°μ΄ κ°μ²΄μμ μ΄μ©νκΈ°
  μ μ¬λ°°μ΄ κ°μ²΄λ Array.prototypeμ λ©μλλ₯Ό μ§μ  μ¬μ©ν  μ μμ. κ·Έλ¬λ Function.prototype.call λ©μλλ‘ κ°μ  νΈμΆνλ©΄ μ¬μ©ν  μ μμ.
  
# π ECMAScript6μ λ°°μ΄κ³Ό μλ‘­κ² μΆκ°λ κΈ°λ₯
  ### π λΉκ΅¬μ‘°ν ν λΉ
  λ°°μ΄, κ°μ²΄, λ°λ³΅ κ°λ₯ κ°μ²΄μμ κ°μ κΊΌλ΄μ΄ κ·Έ κ°μ λ³λμ λ³μμ λμνλ λ¬Έμ₯.
  ### π μ κ° μ°μ°μ
  ...μ μ κ° μ°μ°μλΌ ν¨. λ°λ³΅ κ°λ₯ν κ°μ²΄λ₯Ό λ°ννλ ννμ μμ νκΈ°νλ©°, μ΄λ₯Ό ν΅ν΄ λ°λ³΅ κ°λ₯ν κ°μ²΄λ₯Ό λ°°μ΄ λ¦¬ν°λ΄ λλ ν¨μμ μΈμ λͺ©λ‘μΌλ‘ νΌμΉ  μ μμ
  ```javascript
    [..."ABC"] // ["A","B","C"]
    f(..."ABC") // f("A","B","C")μ κ°μ
  ```
  
  ### π ArrayBufferμ νμν λ°°μ΄
  ArrayBuffer, DataView, νμν λ°°μ΄μ μ°μλ λ°μ΄ν° μμ­(λ²νΌ)μ μ‘°μνκΈ° μν΄ λ§λ€μ΄μ§ κ°μ²΄. μ΄λ€μ νμ©νλ©΄ λ°°μ΄κ³Ό μ΄λ―Έμ§ λ°μ΄ν°λ₯Ό λΉ λ₯΄κ² μ½κ³  μΈ μ μμ.
 
 * ArrayBuffer μμ±μ : λ©λͺ¨λ¦¬μ κ³ μ  κΈΈμ΄λ₯Ό κ°μ§ μΈμ ν μμ­μ νλ³΄. λ¨, λ©λͺ¨λ¦¬μ μμ­μ νλ³΄νλ μ­ν λ§ ν  λΆ λ²νΌλ₯Ό μ‘°μνλ λ©μλλ μ κ³΅νμ§ μμ. 
  * νμν λ°°μ΄ : ArrayBufferκ° νλ³΄ν λ²νΌλ₯Ό λ°μ΄ν°μ μ μ₯ μ₯μλ‘ μ΄λνμ¬ λ°μ΄ν°μ λΉ λ₯Έ μ½κΈ°μ μ°κΈ°λ₯Ό κ΅¬νν κ°μ²΄. 
  * νμν λ°°μ΄κ³Ό μΌλ° λ°°μ΄μ μ°¨μ΄μ 
    - νμν λ°°μ΄ μμμ κ°μλ μ νμ μ΄λ€.
    - νμν λ°°μ΄μ κΈΈμ΄κ° κ³ μ λμ΄ μμΌλ©° μμλ₯Ό μΆκ°νκ±°λ μ­μ ν  μ μλ€.
    - νμν λ°°μ΄μμλ Array.prototypeμ λ©μλλ₯Ό μ¬μ©ν  μ μλ€. νμ§λ§ TypedArray.prototypeμ΄ μ κ³΅νλ λ©μλλ μ¬μ©ν  μ μλ€.
    - νμν λ°°μ΄μ μμ±νλ©΄ λͺ¨λ  μμκ° 0μΌλ‘ μ΄κΈ°νλλ€. 
  
  ### π Map
    - λ°μ΄ν°λ₯Ό μμ§νμ¬ νμ©νκΈ° μν κ°μ²΄. 
    - κ°μ κ³ μ ν μλ³ μ λ³΄μΈ 'ν€'μ κ°μ μμ Map κ°μ²΄ μμ μ μ₯ν΄μ μ¬μ©.
    - Map κ°μ²΄ μμμ ν€λ κ³ μ ν κ°. λ°λΌμ Map κ°μ²΄λ ν€λ‘ κ°μ μ¬μ(Map)ν κ°μ²΄λ‘ κ°μ£Ό.
    - Map κ°μ²΄λ μΈλΆμμ ν€λ₯Ό μ¬μ©νμ¬ μνλ κ°μ μΆκ°/μ­μ /κ²μν  μ μμ. 
    - ν€μ κ°μ λ°μ΄ν° νμμλ μ νμ΄ μμ. κ°μ²΄ νμλ μ¬μ©ν  μ μκ³  μμ νμλ μ¬μ©ν  μ μμ.
    - Map μμ±μ ν¨μλ‘ μμ±νλ€. μΈμλ₯Ό μ§μ νμ§ μμΌλ©΄ λ°μ΄ν°κ° μλ λΉ Map κ°μ²΄κ° μμ±λ¨.
  ```javascript
    var map = new Map();
    console.log(map); // Map {}
  ```
  
  ### π Set
    - μ€λ³΅λμ§ μλ μ μΌν λ°μ΄ν°λ₯Ό μμ§νμ¬ νμ©νκΈ° μν κ°μ²΄.
    - λ°μ΄ν° κ°μ λ¨μ μ§ν©μΌλ‘ κ°μ£Ό.
    - μΈλΆμμ ν€λ₯Ό μ¬μ©νμ¬ λ°μ΄ν° κ°μ μΆκ°/μ­μ /κ²μν  μ μμ.
    - κ°μ λ°μ΄ν° νμμλ μ νμ΄ μμ. κ°μ²΄ νμλ μ¬μ©ν  μ μκ³  μμ νμλ μ¬μ©ν  μ μμ.
    - Set μμ±μ ν¨μλ‘ μμ±νλ€. μΈμλ₯Ό μ§μ νμ§ μμΌλ©΄ λ°μ΄ν°κ° μλ λΉ Set κ°μ²΄κ° μμ±λ¨.
  ```javascript
    var set = new Set();
    console.log(set); // Set {}
  ```

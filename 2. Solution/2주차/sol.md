π€·ββοΈ 
μμ ν¨μ μμμ λ³μμ λΈλ‘ μ ν¨λ²μλ₯Ό κ³΅λΆνλ€κ° μλ let λ¬Έμ κ²½μ°,   
var λ¬ΈμΌλ‘ μ μΈν λ³μλ₯Ό μ½μΌλ €κ³  μλν λ μ€λ₯κ° λ°μνμ§ μλκ²κ³Ό λμ‘°μ μΈκ²μ λ³΄κ³  μλ¬Έμ μ΄ λ€μλ€.
```javascript
console.log(x) // ReferenceError: x is not defined
let x = 5
```
λͺ¨λμλ°μ€ν¬λ¦½νΈμλ¬Έ κ΅μ¬μμ TDZ λλ¬Έμ΄λΌκ³  λμμλλ°, μ΄ν΄κ° μ κ°μ§ μμλ€. μΌλ¨ TDZ μ μλ₯Ό λ³΄κ³  ν¬μ€νμ λ΄λ €κ°λ©΄μ TDZμ λν΄ μ΄ν΄ν΄λ³΄μ.
# TDZ(Temporal Dead Zone) ?
- μ€μ½νμ μμ μ§μ λΆν° μ΄κΈ°ν μμ μ§μ κΉμ§μ κ΅¬κ°μ TDZ(Temporal Dead Zone) = μΌμμ μΈ μ¬κ°μ§λλΌκ³  νλ€.
> μ€μ½ν(Scope) : 'λ³μμ μ κ·Όν  μ μλ λ²μ' ; global(μ μ­) local(μ§μ­)

<br>

## λ³μ μ μΈμ 3λ¨κ³
<p align="center"><img width="30%" src="https://user-images.githubusercontent.com/76654131/138394994-39408b4b-068d-4532-9f68-7f5995aecb35.png"></p>

- μ μΈ λ¨κ³(Declaration phase) : λ³μλ₯Ό μ€ν μ»¨νμ€νΈμ λ³μ κ°μ²΄μ λ±λ‘νλ λ¨κ³λ₯Ό μλ―Ένλ€. μ΄ λ³μ κ°μ²΄λ μ€μ½νκ° μ°Έμ‘°νλ λμμ΄ λλ€.
- μ΄κΈ°ν λ¨κ³(Initialization phase) : μ€ν μ»¨νμ€νΈμ μ‘΄μ¬ νλ λ³μ κ°μ²΄μ μ μΈ λ¨κ³μ λ³μλ₯Ό μν λ©λͺ¨λ¦¬λ₯Ό λ§λλ λ¨κ³. μ΄ λ¨κ³μμ ν λΉλ λ©λͺ¨λ¦¬μλ undefinedλ‘ μ΄κΈ°ν λλ€.
- ν λΉ λ¨κ³(Assignment phase) : μ¬μ©μκ° undefinedλ‘ μ΄κΈ°νλ λ©λͺ¨λ¦¬μ λ€λ₯Έ κ°μ ν λΉνλ λ¨κ³.

> μ€ν μ»¨νμ€νΈ(Execution Context)λ scope, hoisting, this, function, closure λ±μ λμμλ¦¬λ₯Ό λ΄κ³  μλ μλ°μ€ν¬λ¦½νΈμ ν΅μ¬μλ¦¬μ΄λ€.   
μ’ λ μ½κ² λ§νμλ©΄ μ€ν μ»¨νμ€νΈλ μ€ν κ°λ₯ν μ½λκ° μ€νλκΈ° μν΄ νμν νκ²½... μ΄λΌλλ° μμ§ν μ΄ν΄κ° μ μκ°μ λμ€μ λ°λ‘ μ λ¦¬!  [μ°Έκ³ ](https://poiemaweb.com/js-execution-context)

π μ§κΈκΉμ§ μλ¬΄ μκ°μμ΄ var let constλ₯Ό μ¬μ©νλλ°, μμ²λΌ 3κ°μ§ λ¨κ³λ₯Ό κ±°μ³μ μμ±λλ κ²μ μμλ€.

## var λ³μ lifecycle
<p align="center"><img width="50%" src="https://user-images.githubusercontent.com/76654131/138396433-1c4dac06-0098-451e-8b03-19baf5d2f4e9.png">
</p>

- var κ°μ κ²½μ° μ μΈκ³Ό λμμ undefinedλΌλ κ°μΌλ‘ μ΄κΈ°νκ° λλ€. μ¦, μ μΈ λ¨κ³μ μ΄κΈ°ν λ¨κ³λ₯Ό λμμ μ§ν
- κ·Έλ κΈ° λλ¬Έμ λ³μλ₯Ό μ μΈνκΈ° μ μ νΈμΆμ ν΄λ undefinedλ‘ νΈμΆμ΄ λλ νΈμ΄μ€νμ΄ λ°μ!

```javascript
console.log(x) // undefined
var x = 5
```

## let(const) λ³μ lifecycle
<p align="center"><img width="50%" src="https://user-images.githubusercontent.com/76654131/138398124-93fd95dc-fb4c-4315-bff8-e7ba22661832.png"></p>

- let , const λ³μλ€λ μ€νμ»¨νμ€νΈ μμ±λ¨κ³μμ λ©λͺ¨λ¦¬μ λ§€νμ΄ μΌμ΄λλ©΄μ νΈμ΄μ€νμ΄ μΌμ΄λμ§λ§ var λ³μμ λ¬λ¦¬ μ΄κΈ°νλ¨κ³κ° μΌμ΄λμ§ μλλ€.
- κ·Έλμ μ€ν μ»¨νμ€νΈμ λ³μλ₯Ό λ±λ‘νμ§λ§, λ©λͺ¨λ¦¬κ° ν λΉμ΄ λμ§ μμ μ κ·Όν  μ μμ΄ μ°Έμ‘° μλ¬(ReferenceError)κ° λ°μνλ κ²μ΄μλ€.   
λλ μ§κΈκΉμ§ μ΄λ°κ²μ λͺ¨λ₯΄κ³ , κ·Έλ₯ νΈμ΄μ€νμ΄ λμ§ μλκ΅¬λλΌκ³  μ€ν΄λ₯Ό νλκ²μ΄λ€.

π₯ μ¦, let const λν μ μΈλ¨κ³μμ μ€ν μ»¨νμ€νΈ λ³μ κ°μ²΄μ λ±λ‘μ΄ λμ΄ νΈμ΄μ€νμ΄ λμ§λ§,   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TDZ κ΅¬κ°μ μν΄ λ©λͺ¨λ¦¬κ° ν λΉμ΄ λμ§ μμ μ°Έμ‘° μλ¬(ReferenceError) λ°μνλ κ²μ΄λ€.
   
<br>
<br>

**Reference**   
λ³Έ ν¬μ€νμ μλ μ¬μ΄νΈλ₯Ό μ°Έμ‘° λ° μΈμ©νμ¬ κ°μΈκ³΅λΆ μ©λλ‘ μμ±λμμ΅λλ€.   
μλͺ»λ λ΄μ© νΌλλ°± μ£Όμλ©΄ λ°μνκ² μ΅λλ€. κ°μ¬ν©λλ€.   
[https://noogoonaa.tistory.com/78](https://noogoonaa.tistory.com/78)   
[https://caferion.netlify.app/JavaScript/variable/](https://caferion.netlify.app/JavaScript/variable/)

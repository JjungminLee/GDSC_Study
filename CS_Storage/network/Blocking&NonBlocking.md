# Blocking&NonBlocking

### π λ¨μ΄μ λ¦¬

- μ μ΄κΆ: ν¨μμ μ½λλ₯Ό μ€νν  κΆλ¦¬ κ°μ κ². μ μ΄κΆμ κ°μ§ ν¨μλ μμ μ μ½λλ₯Ό λκΉμ§ μ€νν ν, μμ μ νΈμΆν ν¨μμκ² λλ €μ€λ€.
- κ²°κ³Όκ°μ κΈ°λ€λ¦°λ€λ κ²: Aν¨μμμ Bν¨μλ₯Ό νΈμΆνμ λ, Aν¨μκ° Bν¨μμ κ²°κ³Όκ°μ κΈ°λ€λ¦¬λλμ μ¬λΆλ₯Ό μλ―Έ.

## λκΈ°&λΉλκΈ°

- λκΈ°μ λΉλκΈ°λ νλ‘μΈμ€μ μνμμ λ³΄μ₯μ λν λ©μ»€λμ¦μ΄λ€.
- μ²λ¦¬ν  μμλ€μ μ΄λ ν **νλ¦**μΌλ‘ μ²λ¦¬ν  κ²μΈκ°μ λν κ΄μ μ΄λ€.
- ν¨μμ μμ μλ£μ¬λΆλ₯Ό μ κ²½μ°λμ λ°λΌ ν¨μ μ€ν/λ¦¬ν΄ μμ°¨μ μΈ νλ¦μ λ°λ₯΄λλ, μλ°λ₯΄λλμ κ΄μ¬μ¬λ₯Ό λλ€.

### λκΈ°

- μμ²­μκ° μμ²­λ°μ ν¨μμ μμμ΄ μλ£λμλμ§ κ³μ νμΈνλ€.
- μ¬λ¬ ν¨μλ€μ΄ μκ°μ λ§μΆ° μ€νλλ€.
- ν¨μ Aκ° ν¨μ Bμ μμ μλ£ ν λ¦¬ν΄μ κΈ°λ€λ¦¬κ±°λ, λ°λ‘ λ¦¬ν΄ λ°λλΌλ λ―Έμλ£ μνμ΄λ©΄ μμ μλ£ μ¬λΆλ₯Ό μ€μ€λ‘ κ³μ νμΈνλ©° μ κ²½μ°λ©΄ λκΈ°(Synchronous)μ΄λ€.

### λΉλκΈ°

- μμ²­μλ μμ²­ν μΌμ μ κ²½ μ°μ§ μλλ€. μμ²­λ°μ ν¨μκ° μμμ λ§μΉλ©΄ μλ €μ€λ€.
- κ·Έλ κΈ°μ ν¨μλ€μ μμ μμ/μ’λ£ μκ°μ΄ λ§μ§ μμ μλ μλ€.
- ν¨μ Aκ° ν¨μ Bλ₯Ό νΈμΆν  λ μ½λ°± ν¨μλ₯Ό ν¨κ» μ λ¬ν΄μ ν¨μ Bμ μμμ΄ μλ£λλ©΄ ν¨κ» λ³΄λΈ μ½λ°±ν¨μλ₯Ό μ€ννλ€.
- ν¨μ Aλ ν¨μ Bλ₯Ό νΈμΆν ν ν¨μ Bμ μμ μλ£ μ¬λΆμλ μ κ²½μ°μ§ μλλ€.(Aysnchronous)

## λΈλ‘νΉ&λΌλΈλ‘νΉ

- λΈλ‘νΉκ³Ό λΌλΈλ‘νΉμ νλ‘μΈμ€μ μ ν΄ μνμ λν κ°λμ΄λ€.
- μ²λ¦¬λμ΄μΌ νλ νλμ μμμ΄ **μ μ²΄μ μΈ μμ νλ¦μ λ§λλ, μλ§λλ**μ λν κ΄μ μ΄λ€.
- μ μ΄κΆμ΄ λκ΅¬νν μλλμ κ΄μ¬μ¬λ₯Ό λλ€.

### λΈλ‘νΉ

![λΈλ‘νΉ.png](https://user-images.githubusercontent.com/85864699/209420084-2696d330-8c41-4306-90a4-4c4e6269f893.png)

- μμ²­λ°μ ν¨μκ° μμμ λͺ¨λ λ§μΉκ³  λμμΌ μμ²­μμκ² μ μ΄κΆμ λκ²¨μ€λ€.(κ·Έλμ μμ²­μλ μλ¬΄κ²λ νμ§μκ³  κΈ°λ€λ¦°λ€)
- Aν¨μκ° Bν¨μλ₯Ό νΈμΆνλ©΄ **μ μ΄κΆμ Aκ° νΈμΆν Bν¨μμ λκ²¨μ€λ€.**
- μμ
    1. Aν¨μκ° Bν¨μλ₯Ό νΈμΆνλ©΄ Bμκ² μ μ΄κΆμ λκΈ΄λ€.
    2. μ μ΄κΆμ λκ²¨λ°μ Bλ ν¨μλ₯Ό μ€ννκ³ , Aλ Bμκ² μ μ΄κΆμ λκ²¨μ£ΌμκΈ°μ **ν¨μμ€νμ μ μ λ©μΆλ€.**
    3. Bν¨μλ μ€νμ΄ λλλ©΄ μμ μ νΈμΆν Aμκ² μ μ΄κΆμ λλ €μ€λ€.

### λΌλΈλ‘νΉ

![λΌλΈλ‘νΉ.png](https://user-images.githubusercontent.com/85864699/209420094-1b23f997-673e-4bf6-baa6-b064baa2777a.png)

- μμ²­λ°μ ν¨μκ° μμ²­μμκ² μ μ΄κΆμ λ°λ‘ λκ²¨μ€λ€(κ·Έλμ μμ²­μλ λ€λ₯Έ μΌμ ν  μ μλ€)
- Aν¨μκ° Bν¨μλ₯Ό νΈμΆν΄λ **μ μ΄κΆμ κ·Έλλ‘ μμ μ΄ κ°μ§κ³  μλλ€.**
- μμ
    1. Aν¨μκ° Bν¨μλ₯Ό νΈμΆνλ©΄, Bν¨μλ μ€νλμ§λ§, μ μ΄κΆμ Aν¨μκ° κ·Έλλ‘ κ°μ§κ³  μλλ€.
    2. Aν¨μλ κ³μ μ μ΄κΆμ κ°μ§κ³  μκΈ°μ Bν¨μλ₯Ό νΈμΆν μ΄νμλ **μμ μ μ½λλ₯Ό κ³μ μ€ννλ€.**

## λκΈ°&λΉλκΈ° + λΈλ‘νΉ&λΌλΈλ‘νΉ μ‘°ν©

|  | Blocking | NonBlocking |
| --- | --- | --- |
| Synchronous | Sync-Blocking | Sync-NonBlocking |
| Asynchronous | Async-Blocking | Async-NonBlocking |

### Sync-Blocking

- ν¨μ Aλ ν¨μ Bμ λ¦¬ν΄κ°μ νμλ‘ νλ€. (λκΈ°)
- μ μ΄κΆμ ν¨μ Bμ λκ²¨μ£Όκ³ , ν¨μ Bκ° μ€νμ μλ£νμ¬ λ¦¬ν΄κ°κ³Ό μ μ΄κΆμ λλ €μ€λ κΉμ§ κΈ°λ€λ¦°λ€.(λΈλ‘νΉ)
- μμ
    - Cλ JAVA μ½λ μ€ν ν μ»€λ§¨λμμ μλ ₯λ°κΈ°
    
    ```
    A:"μ΄ μΌ λΆνν΄μ."
    B:"λ΅"
    A: Aκ° μΌμ λλ λκΉμ§ κΈ°λ€λ¦Ό
    B:"λλμ΅λλ€~!"
    A:"λ€λΉ~"
    ```
    

Async-Blocking

- Aν¨μλ Bν¨μλ₯Ό νΈμΆνλ€.
- Aν¨μλ Bν¨μμκ² μ μ΄κΆμ μ£Όμ§ μκ³ , μμ μ μ½λλ₯Ό κ³μ μ€ννλ€. (λΌ λΈλ‘νΉ)
- Aν¨μλ Bν¨μμ λ¦¬ν΄κ°μ΄ νμνκΈ° λλ¬Έμ μ€κ°μ€κ° Bν¨μμκ² ν¨μ μ€νμ μλ£νλμ§ λ¬Όμ΄λ³Έλ€. (λκΈ°)
- μμ
    - κ²μμμ λ°μ΄ν° λ‘λμ¨ νμ
        
        ```
        A:"Bμ¨, μ΄ μΌμ’ λΆνν΄μ"
        B:"λ€λ€!"
        A:(ν  κ±° νλ€κ°) "λ€ νμ΄μ?"
        B:"μλ¨! νλμ€μ΄μμ"
        A:(ν  κ±° νλ€κ°) "λ€ νμ΄μ?"
        B:"λ€λ€!"
        ```
        

Async-NonBlocking

- Aν¨μλ Bν¨μλ₯Ό νΈμΆνλ€.
- μ μ΄κΆμ Bν¨μμ μ£Όμ§μκ³ , μμ μ΄ κ³μ κ°μ§κ³  μλλ€. λ°λΌμ Bν¨μλ₯Ό νΈμΆν μ΄νμλ λ©μΆμ§ μκ³  μμ μ μ½λλ₯Ό κ³μ μ€ννλ€. (λΌλΈλ‘νΉ)
- Bν¨μλ₯Ό νΈμΆν λ μ½λ°±ν¨μλ₯Ό ν¨κ» μ€λ€. Bν¨μλ μμ μ μμμ΄ λλλ©΄ Aν¨μκ° μ€ μ½λ°±ν¨μλ₯Ό μ€ννλ€.
- μμ
    - AJAX μμ²­, JS λΉλκΈ° μ½λ°±
    
    ```
    A:"Bμ¨ μ΄ μΌμ’ λΆνν΄μ!"
    B: "λ€~ λ€ νκ³  λ§μ λλ¦΄κ²μ!"
    A: ν κ±° νλ μ€
    B: "λ€ νμ΅λλΉ~~!"
    ```
    

### Async-Blocking

- Aν¨μλ Bν¨μμ λ¦¬ν΄κ°μ μ κ²½μ°μ§ μκ³ , μ½λ°±ν¨μλ₯Ό λ³΄λΈλ€. (λΉλκΈ°)
- κ·Έλ°λ° Bν¨μμ μμμ κ΄μ¬ μμμλ λΆκ΅¬νκ³  Aν¨μλ Bν¨μμκ² μ μ΄κΆμ λκΈ΄λ€. (λΈλ‘νΉ)
- Aν¨μλ μμ κ³Ό κ΄λ ¨μ΄ μλ Bν¨μμ μμμ΄ λλ  λκΉμ§ κΈ°λ€λ €μΌ νλ€.
- μ λ§μ£ΌνκΈ° μ½μ§ μμ κ²½μ°μ΄λ€.
- μμ
    - NodeJS + MySQL μ‘°ν© β NodeJSμμ λΉλκΈ°μ μΌλ‘ DB μμμ μννλλΌλ λΈλ‘νΉ λ°©μμΌλ‘ μλνλ MySQL λλΌμ΄λ²λ₯Ό κ±°μΉκ² λλ€.

## μ°Έκ³ μλ£

[https://inpa.tistory.com/entry/π©βπ»-λκΈ°λΉλκΈ°-λΈλ‘νΉλΌλΈλ‘νΉ-κ°λ-μ λ¦¬](https://inpa.tistory.com/entry/%F0%9F%91%A9%E2%80%8D%F0%9F%92%BB-%EB%8F%99%EA%B8%B0%EB%B9%84%EB%8F%99%EA%B8%B0-%EB%B8%94%EB%A1%9C%ED%82%B9%EB%85%BC%EB%B8%94%EB%A1%9C%ED%82%B9-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC)

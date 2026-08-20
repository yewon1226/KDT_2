## 1) validation check_carrname on save { field Carrname; } 일 때
- 최종 액티브 직전 검증 단계

</br>
</br>

### 소스코드
<img width="608" height="296" alt="image" src="https://github.com/user-attachments/assets/6f1033f1-9d38-49e3-ac82-62125b08ebd3" />
</br>
</br>
</br>
</br>

<img width="518" height="386" alt="image" src="https://github.com/user-attachments/assets/0c2b0031-1c49-4e23-8f26-a375fb5c59df" />
</br>
</br>
</br>
</br>

<img width="737" height="385" alt="image" src="https://github.com/user-attachments/assets/61f10f34-6bcf-4533-b6b0-4f7f180ccc81" />
</br>
</br>
</br>
</br>

### 결과
- Test 입력 후 엔터 쳤을 때 -> `validation check_carrname on save { field Carrname; }` 이므로 `draft determine action Prepare` 를 타서 에러
<img width="1015" height="807" alt="image" src="https://github.com/user-attachments/assets/193ed0b4-2fb9-4918-9a80-ac0336cd21ab" />

</br>
</br>

- 생성 버튼 누를 때 -> `validation check_carrname on save { field Carrname; }` 를 타서 에러
<img width="1142" height="912" alt="image" src="https://github.com/user-attachments/assets/f5b9cc8d-4087-44ac-8ab0-f29bc87826ae" />
</br>
</br>
</br>
</br>

---

</br>

## 2) validation check_carrname on save { create; update; } 일 때
### 코드
<img width="542" height="246" alt="image" src="https://github.com/user-attachments/assets/db3fa463-6927-404e-8069-a22aa34df341" />
</br>
</br>
</br>
</br>

### 결과
- 엔터 쳐도 아무런 에러 안뜸 -> `on save { create; update; }` 이므로
  
<img width="1037" height="284" alt="image" src="https://github.com/user-attachments/assets/e1b708b8-270d-421c-83c8-3f30a839ee14" />
</br>
</br>
</br>
</br>

- 생성 버튼 누를 때 -> `validation check_carrname on save { create; update; }` 를 타서 에러
<img width="1025" height="639" alt="image" src="https://github.com/user-attachments/assets/e115e651-e594-4c9f-a756-b154bef75129" />
</br>
</br>
</br>
</br>

---

</br>

## 3) 오류 두 번 체크 안하는 방법 - optimized

### 소스코드

<img width="631" height="266" alt="image" src="https://github.com/user-attachments/assets/a760b47a-26e6-46d9-b27b-e48b84279320" />

</br>
</br>
</br>
</br>


<img width="857" height="395" alt="image" src="https://github.com/user-attachments/assets/e3b050e2-d56c-4397-8425-53a0b2fbe643" />
</br>
</br>
</br>
</br>

## 결과

- 처음에 값 입력 후 엔터하면 디버깅 탐 : `check_carrname` 

<img width="749" height="395" alt="image" src="https://github.com/user-attachments/assets/bb2c48bc-f608-40c2-8d8e-93836fbafd1a" />

- 값 변경 안하고 생성 버튼 클릭시 디버깅 안타고 바로 생성 : optimized 때문에 carrname에 값이 바뀌지 않으면 `check_carrname`을 안탐. 엔터 후 값 변경 후에 저장하면 `check_carrname`을 탐 
<img width="683" height="204" alt="image" src="https://github.com/user-attachments/assets/29ff1fec-fe99-4592-8bcd-09abed3bf3b6" />
</br>
</br>
</br>
</br>

---

</br>

## 4) 내부적인 에러 메시지 없이 필드 오류 메시지 띄워지는걸 하고싶음 !! -> 꼼수쓰기 (강사님 왈)
### 문제 상황
- 엔터 에러 -> 생성 버튼 클릭 에러 하면 이상한 메시지 뜸 
<img width="1116" height="892" alt="image" src="https://github.com/user-attachments/assets/ddb60b24-04c8-459c-ad12-f2e330195754" />

</br>
</br>
</br>
</br>

### 해결방안
- 검증 로직을 두 번 써라 !
- 엔터 쳤을 땐 failed에 저장하지 않고 생성 버튼 눌렀을 때 failed에 저장하기

<img width="683" height="251" alt="image" src="https://github.com/user-attachments/assets/1c2e4072-5eab-4b60-ba40-d0e4ad40cef0" />
</br>
</br>
</br>
</br>

<img width="743" height="397" alt="image" src="https://github.com/user-attachments/assets/29165e8a-838f-4d39-8a4d-fc44d3349aba" />
</br>
</br>
</br>
</br>

<img width="786" height="362" alt="image" src="https://github.com/user-attachments/assets/fc85bd5b-2eba-474f-bcf3-a0cf786dec10" />
</br>
</br>
</br>
</br>

### 결과

<img width="1130" height="682" alt="image" src="https://github.com/user-attachments/assets/411ce849-84e5-4afb-b623-e81d7c7f4482" />
</br>
</br>
</br>
</br>

---

</br>

## 5) 오류 나고 뒤로 가기 해서(드래프트 버전 생성됨) 생성 버튼 누르면 에러 

<img width="1105" height="657" alt="image" src="https://github.com/user-attachments/assets/ab3fa1ce-ae63-41bf-9286-475bd69a1c89" />
</br>
</br>
</br>
</br>

#### 해결방안 -> 필수값 쓰기 
- 필수값 설정을 하면 에러 메세지보다 우선되어서 눈속임 할 수 있음
```abap
field ( mandatory : create ) Carrid;
```

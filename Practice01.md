## 1) validation check_carrname on save { field Carrname; } 일 때

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
- 엔터 쳤을 때 -> `validation check_carrname on save { field Carrname; }` 이므로 `draft determine action Prepare` 를 타서 에러
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

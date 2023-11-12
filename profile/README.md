## 팀명
YouQuiz
## 제출 타입 및 주제
C타입 : 포스트 코로나 시대의 혼란을 해결하는 SW 개발

## 프로젝트 한 줄 설명
청소년들의 디지털 문해력 부족으로 인한 디지털 콘텐츠 속 정보 습득의 혼란을 해결하기 위해 공공 교육 웹서비스를 통해 해결


## 프로젝트에 활용된 기술

### `SpringBoot` 로 WAS 구현
- 16개의 api 를 구현 
- jpa/hibernate 를 통한 ORM 구현
<img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=for-the-badge&logo=Spring Boot&logoColor=white"> 
<img src="https://img.shields.io/badge/Apache Tomcat-F8DC75?style=for-the-badge&logo=Apache Tomcat&logoColor=black"> 
 
### `Redux-toolkit`으로 상태 관리
-_로그인 시 user의 type(student, teacher)과 id 등 정보를 저장_<br>
-_각 user에 적합한 정보 할당_<br>
-_각 퀴즈 챕터의 데이터를 불러오기_<br>

>store.jsx
```JavaScript
const reducers = combineReducers({
  auth: authSlice.reducer,
  chap: chapSlice.reducer,
  teacher: teacherSlice.reducer,
  result: resultSlice.reducer,
  chap_id: chapIdSlice.reducer,
  register: registerSlice.reducer,
});
  
const persistConfig = {
  key: "root",
  storageSession,
};
const persistedReducer = persistReducer(persistConfig, reducers);

export const store = configureStore({
  reducer: persistedReducer,
  devTools: process.env.NODE_ENV !== "production",
  middleware: [thunk],
});
```
>index.jsx
```JavaScript
import { Provider } from 'react-redux';
import { store } from "./store/store";

<Provider store={store}>
...
</Provider>
```
<img src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=React&logoColor=white">
<img src="https://img.shields.io/badge/Redux-764ABC?style=for-the-badge&logo=Redux&logoColor=white">

### `AWS` 서비스를 이용한 아키텍쳐 구축/배포
- EC2, RDS FreeTier 인스턴스를 통한 서버, DB storage 구축 (DB는 Mysql 사용)
- docker 를 통한 SpringBoot/React Project 실행 (자체 이미지가 아닌 상용 이미지를 pull 하여 서버 내에서 실행파일을 직접 build 하여 execute)
- Nginx 를 통한 reverse-proxy 를 구현
- https 프로토콜 적용
 
<img src="https://img.shields.io/badge/Amazon EC2-FF9900?style=for-the-badge&logo=Amazon EC2&logoColor=white"> 
<img src="https://img.shields.io/badge/Amazon RDS-527FFF?style=for-the-badge&logo=Amazon RDS&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=white">
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=Docker&logoColor=white">  
<img src="https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=NGINX&logoColor=white">  


## 시연 영상


## 팀원 및 참고 자료
<table>
  <tbody>
    <tr>
      <td align="center"><a href="https://github.com/himodu"><img src="https://avatars.githubusercontent.com/u/71763322?v=4" width="100px;" alt=""/><br /><sub><b>BE 팀장 : 이동건 (himodu)</b></sub></a><br /></td>
      <td align="center"><a href="https://github.com/SubinPyeon"><img src="https://avatars.githubusercontent.com/u/105070397?v=4" width="100px;" alt=""/><br /><sub><b>BE 팀원 : 편수빈 (SubinPyeon) </b></sub></a><br /></td>
      <td align="center"><a href="https://github.com/Hyoeunkh"><img src="https://avatars.githubusercontent.com/u/102338613?s=64&v=4" width="100px;" alt=""/><br /><sub><b>FE 팀원 :  이효은 (Hyoeunkh) </b></sub></a><br /></td>
      <td align="center"><a href="https://github.com/wjdqh6544"><img src="https://avatars.githubusercontent.com/u/77498822?v=4" width="100px;" alt=""/><br /><sub><b>BE 팀원 : 서형철 (wjdqh6544) </b></sub></a><br /></td>
    </tr>
  </tbody>
</table>


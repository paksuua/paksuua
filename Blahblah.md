<h2 align="center">
🧡 BlahBlah 🧡
</h2> 

<div align="center" style="display:flex;">
	<img width="300" height="300" alt="wooly_logo" src="https://user-images.githubusercontent.com/43838030/116832947-c1b0f580-abf1-11eb-8838-5b27e26aec14.JPG">
</div>
<div align="center">
🗣 Blahblah_Android 💻
</div>

---
영화와 드라마와 같은 영상 매체 기반으로 자막 및 STT를 통한 쉐도잉 학습 및 복습 기능을 제공하는 영어 학습 서비스입니다 <br> 

&nbsp;

## 🧡 서비스 주요 기능
  1. **영상 학습**: 영상이 제생되며 문장마다 정지되고 사용자가 대답하며 대화 연습을 할 수 있습니다. (자막 생성 여부 선택 가능)
  2. **쉐도잉 학습**: 영상의 각 문장 재생 직후 해당 문장을 따라 말하며 쉐도잉 학습을 진행할 수 있습니다. 진행된 학습 내용이 녹음됩니다.
  3. **챗봇 대화 학습**: Google Dialogflow를 이용하여 사전에 학습시킨 대화 모델을 기반으로 간단한 회화 연습을 할 수 있습니다.
  4. **연습문제 & 단어학습**: 앞서 진행한 학습 데이터를 기반으로 연습문제와 단어학습을 통한 복습 기능을 제공합니다.
  5. **학습 음성 확인**: 쉐도잉 학습시 녹음된 음성을 다시 확인할 수 있습니다.

------

### 📄 Service Work Flow
![워크플로우](https://user-images.githubusercontent.com/43838030/116833290-6bdd4d00-abf3-11eb-9502-de75a7303009.JPG)

# Blahblah_Android :loudspeaker:

### 👩🏻‍🤝‍👩🏻 개발 담당

| 이름                                                  | 담당                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------- |
| 박소연 | 영상 학습, Shadowing 학습, Google Dialogflow 연동, 학습 음성 확인 |
| 서예슬 | 연습문제 및 단어학습, 회원가입, 로그인, 영상 목록 리스트 |

------
&nbsp;


<!--| 이름                                                  | 담당                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------- |
| 신승민 | Core 알람,  소셜 로그인 연동(kakao, facebook), 회원가입 |
| 박소연 | 다짐 목록, 다짐 히스토리, 자체 로그인, 개인정보 수정 |-->



### 🛠 1. Skills
**Java, Media Player, File I/O, SQLite, MPChart , RecyclerView , STT, Google Dialogflow**
<!--
### 📚 2.프로젝트 사용 라이브러리
| 라이브러리                                                   | 목적                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------- |
| [Coroutine](https://developer.android.com/topic/libraries/architecture/coroutines) | 비동기 처리 및 통신 |
| [KTX](https://developer.android.com/kotlin/ktx?hl=ko) | AAC를 위한 LifeCycle 관리 |
| Dagger - Hilt | 의존성 주입 |
| Room - DataStore | 로컬 DB에 알람 객체 및 다짐 데이터 저장  |
| Lottie | 애니메이션 적용 |
| [Gson](https://github.com/google/gson) | JSON 객체 Converter |
| [Glide](https://github.com/bumptech/glide) | 이미지 포멧팅 |
| [Retrofit](https://square.github.io/retrofit/) | HTTP 통신 |
### 🔀 3. Commit Convention
## 😜[Gitmoji](https://gitmoji.dev/)
<div align="left"><img width="400" height="400" alt="wooly_logo" src="https://user-images.githubusercontent.com/43838030/116831425-49930180-abea-11eb-89af-e0780b88e0d1.JPG"></div>
-->

### 📚 2. Activity 구조
|                  Activity   |                 Description   |
| ----------------------------------- | ------------------------------------------- |
| LoginActivity  |  로그인  |
| SignupActivity  |  회원가입  |
| VideoActivity  | 영상의 문장에 대답하고 STT로 대답을 확인하는 영상학습 진행 |
| ShadowingActivity  | 영상 속 문장을 따라 말하는 Shadowing 학습 진행, 학습 결과가 자동 녹음됨 |
| ChatbotActivity  | 사전 학습시킨 Google Dialogflow 를 이용한 챗봇 구현 |
| ReviewActivity  |  학습 영상에 포함된 주요 문장 스피킹 학습 |
| ReviewWordActivity  |  학습한 영상에 포함된 주요 단어 학습 |
| VideoLearnActivity  | 영상 학습시 저장된 녹음 및 STT 텍스트로 복습 |


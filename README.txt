변형 체스 안드로이드 앱 (APK) 만들기
=====================================

이 폴더는 게임(app/src/main/assets/index.html)을 그대로 담은 안드로이드 앱 프로젝트예요.
APK를 만들어 휴대폰에 직접 설치하면 플레이 스토어나 브라우저 없이 아이콘으로 실행돼요.

[방법 1] GitHub이 대신 만들어 주기 (PC에 아무것도 설치 안 해도 됨)
 1. github.com에서 새 저장소(Private 추천)를 만들고, 이 폴더 안의 내용을 통째로 올려요.
    (.github 폴더도 꼭 같이 올라가야 해요. 웹에서 "uploading an existing file"로 끌어다 놓아도 돼요.)
 2. 저장소의 Actions 탭 → "Build APK" → Run workflow (올리기만 해도 자동으로 한 번 돌아요).
 3. 5분쯤 뒤 초록 체크가 뜨면 그 실행을 눌러 맨 아래 "변형체스-apk"를 내려받고 압축을 풀면 app-release.apk가 있어요.

[방법 2] 내 PC에서 만들기
 1. Android Studio(무료)를 설치하고 File → Open으로 이 폴더를 열어요. 처음엔 필요한 파일을 받느라 몇 분 걸려요.
 2. 메뉴 Build → Build App Bundle(s) / APK(s) → Build APK(s).
 3. app/build/outputs/apk/release/app-release.apk 가 생겨요.

[휴대폰에 설치]
 1. APK 파일을 휴대폰으로 옮겨요 (USB 연결, 카카오톡 나에게 보내기, 구글 드라이브 등).
 2. 휴대폰 파일 앱에서 APK를 눌러요. "출처를 알 수 없는 앱" 경고가 나오면 설정에서 그 앱(파일 앱 등)에 설치 허용을 켜고 다시 눌러요.
 3. 설치가 끝나면 홈 화면에 "변형 체스" 아이콘이 생겨요.

[알아 둘 점]
 - 게임 파일이 앱 안에 들어 있어서 인터넷 없이 로컬 대전, AI 대전이 돼요. 온라인 대국과 로그인은 인터넷이 필요해요.
 - 게임을 고친 뒤에는 새 index.html을 app/src/main/assets/에 덮어쓰고, app/build.gradle의 versionCode를 1씩 올려서 다시 만들면
   기존 앱 위에 업데이트로 설치돼요(같은 서명 키 cardchess.jks를 쓰기 때문에 지우지 않아도 돼요). cardchess.jks는 지우지 마세요.
 - 아이폰은 애플 정책상 앱 스토어 없이 설치하는 방법이 사실상 없어요(맥과 Xcode가 있으면 7일짜리 개인 설치만 가능).

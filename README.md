# 설원 렌탈 · GitHub Pages 배포

1. ZIP을 풀고 `docs` 폴더와 `README.md`, `firestore.rules`를 GitHub 저장소 루트에 업로드합니다. ZIP 자체는 업로드하지 않습니다. `docs/index.html`과 `docs/app-config.js`가 같은 폴더에 있어야 합니다.
2. GitHub 저장소의 **Settings → Pages**에서 **Deploy from a branch → main → /docs → Save**를 선택합니다. 다른 브랜치에 업로드했다면 해당 브랜치를 선택합니다.
3. Pages에 표시된 HTTPS 주소를 엽니다. 일반적인 프로젝트 주소는 `https://계정.github.io/저장소/`입니다.

## Firebase 설정

- 기존 Firebase 프로젝트 `intrepid-graph-0ggh3`에 연결됩니다. Authentication의 이메일/비밀번호 로그인과 Firestore 기본 데이터베이스가 필요합니다.
- GitHub 업로드는 Firestore 규칙을 게시하지 않습니다. 아직 게시하지 않았다면 Firebase 콘솔 **Firestore Database → 규칙**에서 현재 규칙과 비교한 후 `firestore.rules`를 적용합니다. 이 파일에는 이전에 제공된 기존 규칙과 스키 앱의 사용자별 접근 규칙이 들어 있습니다.
- Gemini를 쓰려면 조직 관리자가 `firebasevertexai.googleapis.com` 사용을 허용하고, Firebase 프로젝트에서 **AI Logic → Gemini Developer API** 설정을 완료해야 합니다.
- reCAPTCHA Enterprise의 허용 도메인에 실제 Pages 호스트(예: `계정.github.io`)를 등록합니다. Firebase App Check에 웹 앱을 등록하고, `docs/app-config.js`에 **공개 사이트 키**를 넣어 다시 커밋합니다. 서비스 계정 키나 비공개 자격 증명은 업로드하지 않습니다.
- 배포 주소에서 로그인, 대여, 사진 판독, 반납 확정을 차례로 테스트합니다.

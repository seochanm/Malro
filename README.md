# Malro

## 프로젝트 개요
Malro는 AI 기반 영어 발음 학습 및 번역 지원 애플리케이션입니다.  
단순한 "좋음/나쁨" 평가를 넘어, 음절 단위의 상세 발음 피드백을 제공하여 학습자가 자신의 발음을 구체적으로 교정할 수 있도록 돕습니다.  

- 주요 기능:
  - 카카오 계정 기반 로그인
  - 음성 입력 & 실시간 번역 (Azure Translator API)
  - AI 음성 합성 (Google TTS)
  - 발음 학습 및 피드백 (TheFluent API)
  - 학습 기록 저장/조회 (Firebase Firestore & Storage)

---

## 실행 방법
1. 저장소 클론
   ```bash
   git clone https://github.com/seochanm/Malro.git
2. Android Studio에서 프로젝트 열기
3. Gradle Sync 완료 후 SDK/Build-Tools 설치
4. app/google-services.json 파일 배치 (Firebase 설정)
5. local.properties에 API 키 입력
properties
AZURE_ENDPOINT=...
AZURE_KEY=...
AZURE_REGION=...
THEFLUENT_BASE=...
6. 에뮬레이터 또는 USB 연결된 안드로이드 기기에서 실행

## 앱 사용 흐름
오늘의 문장 학습
LoginActivity → MainActivity → TodayPronunciationActivity → TodayStudyFeedbackActivity

번역 학습
TranslateActivity → TranslateStudyActivity → TranslatePronunciationActivity → TranslateFeedbackActivity

레벨별 학습
StudyStartActivity → StudyPronunciationActivity → StudyFeedbackActivity

아카이브(기록)
ArchiveTranslationActivity → 과거 학습 기록 확인

## 개발 환경
Android Studio Narwhal 2025.1.1

Gradle JDK: JetBrains Runtime 21.0.6

Java 11 / Android SDK (minSdk 24 / targetSdk 35 / compileSdk 35)

Firebase, Kakao SDK, Google Cloud STT/TTS, Azure Translator, TheFluent API

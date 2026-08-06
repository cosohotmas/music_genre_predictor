# 🎵 음악 장르 예측 앱 (Music Genre Prediction App)

> **Streamlit으로 구현한 음악 장르 분류 웹 앱** — WAV 파일을 업로드하면 AI가 장르를 예측해줍니다.

## 🚀 빠른 시작

### 로컬에서 실행하기

```bash
# 1. 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate

# 2. 의존성 설치
pip install --upgrade pip
pip install -r requirements.txt

# 3. 앱 실행
streamlit run app.py
```

브라우저가 자동으로 열리면 **WAV 파일을 업로드**하거나 **샘플 파일을 선택**하여 장르 예측을 체험해보세요!

### Streamlit Cloud 배포

1. 이 저장소를 **Fork**하거나 **Clone**합니다.
2. [Streamlit Cloud](https://streamlit.io/cloud)에 로그인합니다.
3. "New app" → GitHub 저장소 선택 → `app.py` 지정 → "Deploy" 클릭!

## 📁 프로젝트 구조

```
ai_music/
├── app.py                          # 🎯 Streamlit 메인 앱
├── app_v2.py                       # 7강 업그레이드 버전 (신뢰도 + 이력 + 멀티파일)
├── app_preview.py                  # 6강 초안 (데모용)
├── model_rf.joblib                 # 학습된 RandomForest 모델
├── label_encoder.joblib            # 레이블 인코더 (장르 문자열 ↔ 숫자)
├── scaler.joblib                   # StandardScaler (피처 정규화)
├── requirements.txt                # Python 의존성
├── packages.txt                    # Streamlit Cloud 시스템 패키지
├── README.md                       # 이 파일
├── Data/
│   ├── Music_genres/
│   │   ├── features_3_sec.csv      # 3초 클립 오디오 피처 (57개 컬럼)
│   │   ├── features_30_sec.csv     # 30초 클립 오디오 피처
│   │   ├── genres_original/        # GTZAN 원본 WAV (10장르 × 100개)
│   │   └── images_original/        # 스펙트로그램 이미지
    └── latest_music_local/         # 데모용 최신 음악

```

## 🎯 지원 장르 (10종)

| 장르 | 이모지 |
|------|--------|
| blues | 🎸 |
| classical | 🎻 |
| country | 🤠 |
| disco | 🪩 |
| hiphop | 🎤 |
| jazz | 🎷 |
| metal | 🤘 |
| pop | 🎵 |
| reggae | 🌴 |
| rock | 🎸 |

## 🔧 기술 스택

- **프론트엔드**: Streamlit
- **오디오 처리**: librosa
- **머신러닝**: scikit-learn (RandomForest)
- **시각화**: matplotlib, seaborn
- **모델 저장**: joblib

## 📊 모델 정보

- **알고리즘**: Random Forest Classifier (100 trees)
- **피처**: 57개의 오디오 특징량 (Chroma, RMS, Spectral Centroid, MFCC 등)
- **정확도**: 약 86% (GTZAN 테스트 세트 기준)
- **데이터 증강**: 3초 클립에서 랜덤 구간 추출 후 앙상블

## 💡 사용 방법

1. **방법 1**: 왼쪽 드롭다운에서 샘플 파일 선택
2. **방법 2**: "Browse files" 버튼으로 직접 WAV 파일 업로드
3. AI가 **Top-3 장르 예측**과 **확률**을 보여줍니다
4. **멜스펙트로그램** 이미지로 시각화 결과 확인

## 📝 라이선스

- **GTZAN Dataset**: 학술 비상업 목적 사용 (Tzanetakis & Cook, 2002)
- **코드**: 자유롭게 사용 및 수정 가능

## 👨‍🏫 교육 자료

이 앱은 **AI Human 개발자 과정**의 6강 "Streamlit으로 장르 예측 앱 만들기" 실습 결과물입니다.
- 강사: 김생근 (KDT 부트캠프 / 이스트소프트)
- 학습 노트북: `강의_AI_Pair/6강_Streamlit_장르예측앱(AI_Pair).ipynb`

---

🎵 **음악으로 AI를 만나보세요!** 🎵

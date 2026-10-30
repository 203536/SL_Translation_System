# SL_Translation_System

Sign Language Translation System for Public Institutions

공공기관 창구에서 청각장애인의 수어를 AI로 인식해 직원 PC에 텍스트로 보여주고, 직원의 답변을 모니터에 띄워주는 양방향 소통 시스템입니다.

- 개발 기간: 2026-10-30 ~ 2026-12-14
- 팀: 4명
- 기술: Python, OpenCV, MediaPipe, TensorFlow(TFLite), Raspberry Pi, Flask

📄 [개발계획서](docs/DEVELOPMENT_PLAN.md) · 📝 [회의록](docs/meeting/)

## 폴더 구조

```
SL_Translation_System/
├── docs/
│   ├── DEVELOPMENT_PLAN.md   # 개발계획서
│   └── meeting/              # 회의록 (YYYY-MM-DD.md)
├── data/
│   ├── raw/                  # 원본 영상 (Git 제외, Google Drive 보관)
│   ├── keypoints/            # 단어별 좌표 시퀀스 (.npy)
│   └── labels.csv            # 단어 목록
├── src/
│   ├── data_collection/      # 촬영·좌표 추출 (데이터 파트)
│   ├── model/                # 학습·평가·TFLite 변환 (모델 파트)
│   ├── pi/                   # 라즈베리파이 실시간 인식 (파이 파트)
│   └── staff_app/            # 직원 화면·통신 서버 (화면·통신 파트)
├── models/                   # 학습된 모델 (.tflite)
├── tests/                    # 테스트 코드
└── requirements.txt
```

## 개발 환경 설정

```bash
git clone https://github.com/203536/SL_Translation_System.git
cd SL_Translation_System
python -m venv venv
# Windows: venv\Scripts\activate   /   macOS·Linux·Pi: source venv/bin/activate
pip install -r requirements.txt
```

## 협업 규칙

- **브랜치**: `main`(시연용) / `develop`(통합) / `feature/기능명`
- **커밋 메시지**: `feat:` `fix:` `docs:` `refactor:` `data:` `model:`
- **작업 관리**: GitHub Issues + Projects
- **영상·데이터셋은 절대 커밋하지 않기** (얼굴이 나오는 개인정보, public 저장소)

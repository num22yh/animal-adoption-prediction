# 유기동물 입양 속도 예측

- 목표: 동물 정보를 이용한 입양 속도 예측 및 모델별 성능 비교
- Target: AdoptionSpeed 0~4
- 모델: Gradient Boosting, AdaBoost, LightGBM, XGBoost, CatBoost
- 평가 지표: Accuracy, Macro F1, 클래스별 Precision, Recall, F1

## 파일 구성

```text
animal-adoption-prediction/
├─ README.md
├─ requirements.txt
├─ notebooks/
│  └─ 01_modeling_workflow.ipynb
└─ data/
   ├─ train.csv
   └─ BreedLabels.csv
```

- [실험 노트북](notebooks/01_modeling_workflow.ipynb): 분석 코드, 모델 학습, 평가 결과
- `train.csv`: 동물 프로필 14,993건 및 입양 속도 클래스
- `BreedLabels.csv`: 품종 코드와 품종명

## 실행 환경

- 검증 환경: Windows, Python 3.11.7
- 노트북 실행: VS Code의 Python 및 Jupyter 확장 또는 JupyterLab

| 라이브러리 | 검증 버전 | 용도 |
|---|---|---|
| numpy | 2.4.6 | 수치 연산 |
| pandas | 3.0.6 | 데이터 처리 |
| scipy | 1.17.1 | 수치 계산 의존성 |
| scikit-learn | 1.9.1 | 전처리, 교차검증, 모델 학습, 평가 |
| matplotlib | 3.11.2 | 시각화 |
| xgboost | 3.2.0 | XGBoost 학습 |
| lightgbm | 4.7.0 | LightGBM 학습 |
| catboost | 1.2.10 | CatBoost 학습 |
| category-encoders | 2.11.1 | 품종 Binary Encoding |
| ipykernel | 7.3.0 | Python 노트북 커널 |

- 전체 직접 의존성과 버전: [requirements.txt](requirements.txt)
- nbformat, nbclient, jupyter-client, jupyter-core: 노트북 실행 및 검증 도구

## 실행 방법

### 1. 가상환경 생성 및 라이브러리 설치

저장소 루트에서 실행:

```powershell
python -m venv .venv
.venv\Scripts\python.exe -m pip install -r requirements.txt
```

- macOS/Linux의 Python 실행 경로: `.venv/bin/python`

### 2. 노트북 실행

1. VS Code에서 저장소 폴더 열기
2. `notebooks/01_modeling_workflow.ipynb` 열기
3. 커널 선택에서 `.venv`의 Python 선택
4. 커널 재시작 후 전체 셀 실행

JupyterLab 사용 시 추가 설치 및 실행:

```powershell
.venv\Scripts\python.exe -m pip install jupyterlab
.venv\Scripts\python.exe -m jupyter lab
```

- 데이터 경로: 저장소 루트의 `data/` 폴더
- 결과 저장 경로: 실행 중 자동 생성되는 `results/current/`
- 노트북 자체에 저장된 표와 그래프를 통한 실행 결과 확인
- 재실행 시 결과 파일과 노트북 출력 갱신
- 파라미터 탐색에 따른 실행 시간 발생

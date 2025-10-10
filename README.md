# 프로젝트 이름

<br>

## 💻 프로젝트 소개
### <프로젝트 소개>
- _24시간 단위의 비트코인 시계열 데이터를 기반으로, 다음 1시간의 비트코인 시가를 예측하는 시계열 예측 프로젝트입니다. 실시간 데이터 수집부터 모델 학습, 배포, 모니터링까지 MLOps 파이프라인을 구성하여 예측 정확도를 높이고 안정적인 모델 운영을 목표로 하였습니다._

### <작품 소개>
- _본 프로젝트에서는 Airflow를 활용한 데이터 파이프라인 구축, MLflow를 통한 모델 관리 및 버전 관리, Docker와 Streamlit을 활용한 모델 배포 및 시각화 환경을 구현했습니다. 24시간 데이터를 기반으로 예측 모델을 학습하고, 예측값과 모델 성능을 시각화하여 사용자가 쉽게 확인할 수 있는 인터랙티브한 예측 시스템을 제공합니다._

<br>

## 👨‍👩‍👦‍👦 팀 구성원
| ![박준수](https://avatars.githubusercontent.com/u/156163982?v=4) | ![정무곤](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김수현](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김예인](https://avatars.githubusercontent.com/u/156163982?v=4) | ![오정택](https://avatars.githubusercontent.com/u/156163982?v=4) |
| :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
| [박준수](https://github.com/parkjunsu3321) | [정무곤](http://github.com/mugon-jeong) | [김수현](https://github.com/Daisy7942) | [김예인](https://github.com/yeondu-0) | [오정택](https://github.com/Jeong5689) |
| 팀장, Modeling / 서비스 배포| DataPipeLine / MLFlow 서버 구축 | DataPipeLine/모델 배포 | Modeling / 모델 배포 | Data Preprocessing / EDA |

<br>

## 🔨 개발 환경 및 기술 스택
- 주 언어 : _python_
- 버전 및 이슈관리 : _github_
- 협업 툴 : _ github, notion, slack_

<br>

## 📁 프로젝트 구조
```
├── .gitignore
├── data_load_from_s3.py
├── model2.ipynb
├── modeling.ipynb
├── README.md
├── .github
│   └── workflows
│       ├── deploy.yml
│       └── retrain.yml
├── airflow
│   ├── .env.example
│   ├── docker-compose.yaml
│   ├── Dockerfile
│   ├── entrypoint.sh
│   ├── requirements.txt
│   └── dags
│       ├── hourly_compact_upload.py
│       ├── ingest_10s.py
│       └── common
│           ├── manifest.py
│           ├── s3io.py
│           └── utils.py
├── final_code
│   ├── data_loader.py
│   ├── data_preprocessor.py
│   ├── Dockerfile
│   ├── inference.ipynb
│   ├── mlflow_model_manager.py
│   ├── requirements.txt
│   ├── s3_loader.py
│   ├── training.py
│   ├── training2.py
│   └── training2_local.py
├── mlflow
│   ├── .env.template
│   ├── docker-compose.yaml
│   ├── Dockerfile
│   └── tutorial.py
├── services
│   ├── docker-compose.yml
│   ├── back
│   │   ├── .env
│   │   ├── .gitignore
│   │   ├── Dockerfile
│   │   ├── main.py
│   │   ├── README.md
│   │   ├── requirements.txt
│   │   ├── api
│   │   │   ├── routes_predict.py
│   │   │   ├── __init__.py
│   │   │   └── __pycache__
│   │   │       ├── routes_predict.cpython-311.pyc
│   │   │       ├── routes_predict.cpython-312.pyc
│   │   │       ├── __init__.cpython-311.pyc
│   │   │       └── __init__.cpython-312.pyc
│   │   ├── core
│   │   │   ├── config.py
│   │   │   ├── utils.py
│   │   │   └── __pycache__
│   │   │       ├── config.cpython-312.pyc
│   │   │       ├── utils.cpython-311.pyc
│   │   │       └── utils.cpython-312.pyc
│   │   └── __pycache__
│   │       └── main.cpython-312.pyc
│   └── streamlit_ui
│       ├── .env
│       ├── app.py
│       ├── Dockerfile
│       └── requirements.txt
└── upbit-ticker
    ├── .env.template
    ├── docker-compose.yaml
    ├── Dockerfile
    └── src
        ├── config.py
        ├── main.py
        ├── parquet_appender.py
        ├── requirements.txt
        ├── s3_uploader.py
        └── upbit_client.py

```

<br>

## 💻​ 구현 기능
### 기능1
- _현재 시간 기반 30시간 데이터 로드 및 24시간 데이터 시각화_
### 기능2
- _24시간 데이터를 기반으로 다음 1시간 예측_
### 기능3
- _예측값 및 모델 성능 시각화_

<br>

## 🛠️ 작품 아키텍처
![title](https://private-user-images.githubusercontent.com/127470862/499683787-71cadf33-f8fb-443a-bdc1-01515ad85f41.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjAwNzIyMjAsIm5iZiI6MTc2MDA3MTkyMCwicGF0aCI6Ii8xMjc0NzA4NjIvNDk5NjgzNzg3LTcxY2FkZjMzLWY4ZmItNDQzYS1iZGMxLTAxNTE1YWQ4NWY0MS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUxMDEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MTAxMFQwNDUyMDBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0xNWE2YWI1Y2U2N2EwMGIwNDllMWYxMjMzMGU1MTBhMzZhMDM4M2Y1MjYwNGI3Y2U4NzQxNDcxMjVjZjQ2NDdhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.bqAHD90RIK0FV2r7Mn6-d1--3aofx_kkV-mZH0EngXo)   


## 📌 프로젝트 회고
### 박준수
- _MLOps 프로젝트를 통해서 MLOps의 흐름을 경험해볼 수 있어서 좋았습니다. 또한 MLOps 중에 사용되는 툴들에 대해서 공부를 해보고 써볼 수 있어서 좋았습니다._
### 정무곤
- _전체적인 mlops를 경험해 볼 수 있어서 좋았습니다_
### 김예인
- _AWS S3, mlflow 등 처음 접해보는 도구들이 많아서 어려움도 있었지만 결과물을 만들어낼 수 있어서 뿌듯했습니다. AI 개발자가 되기 위해서는 배워야 할 게 참 많다는 생각도 들어서 더 열심히 해야겠다는 마음이 생겼습니다._
### 김수현
- _이번 프로젝트에서 저는 기술적인 부분에서 어려움을 겪으면서 실질적인 개발 기여보다는 주로 회의 참여와 의견 공유에 집중하게 되었습니다. 하지만 회의와 팀 진행 상황을 꾸준히 관찰하고 참여하며, 팀이 어떻게 문제를 해결하고 의사결정을 하는지 배울 수 있었습니다. 이번 경험을 통해 제 역량의 부족함을 확인했고, 앞으로 학습과 준비를 통해 더 적극적으로 참여할 수 있도록 노력하겠습니다._
### 오정택
- _이번 프로젝트는 머신러닝 모델의 학습, 배포, 모니터링을 자동화하기 위한 MLOps 파이프라인 구축을 목표로 진행하였습니다.  Airflow, MLflow, Docker, Streamlit 등 여러 툴을 연동하는 과정에서 컨테이너 간 통신과 환경 변수 관리가 까다로웠습니다. 팀원들에게 도움을 주지 못하고 배우는 데 너무 급급했던 것 같습니다._
<br>

## 📰​ 참고자료
- _https://docs.streamlit.io/_
- _https://fastapi.tiangolo.com/ko/_
- _https://mlflow.org/docs/latest/ml/_
- _https://www.tensorflow.org/api_docs/python/tf/keras/layers/LSTM_
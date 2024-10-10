![header](https://capsule-render.vercel.app/api?type=waving&color=87CEEB&height=300&section=header&text=Welcome!&desc=This%20is%20Dog%20Image%20Classification🐶&fontSize=60&descSize=30&fontColor=ffffff&fontAlignY=40)

## 🛠️기술 스택
<img src="https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat&logo=Python&logoColor=F5F7F8"/>  <img src="https://img.shields.io/badge/Streamlit-1.39.0%2B-FF4B4B?style=flat&logo=Streamlit&logoColor=white"/>  <img src="https://img.shields.io/badge/FastAPI-0.115.0%2B-009688?style=flat&logo=FastAPI&logoColor=white"/>  <img src="https://img.shields.io/badge/Apache_Airflow-017CEE?style=flat&logo=Apache-Airflow&logoColor=white"/>  <img src="https://img.shields.io/badge/PySpark-3.x-E25A1C?style=flat&logo=Apache-Spark&logoColor=white"/>  <img src="https://img.shields.io/badge/PyMySQL-1.1.1%2B-4479A1?style=flat&logo=MySQL&logoColor=white"/>

## Code
- Model 코드 확인 👉🏻 [바로가기](https://github.com/nagazo/deep_fast)
- Airflow 코드 확인 👉🏻 [바로가기](https://github.com/nagazo/airflow_dag)
- Streamlit 코드 확인 👉🏻 [바로가기](https://github.com/nagazo/stream_dog)

## 📚 목차
1. [프로젝트 개요](#프로젝트-개요)
2. [아키텍처 개요](#🏗️-아키텍처-개요)
3. [주요 기능](#🎯-주요-기능)
4. [시스템 구성 요소](#📋-시스템-구성-요소)
5. [설치 방법](#🚀-사용-방법)
6. [라이센스](#📄-라이센스) 
7. [문의](#💬-문의)

## 프로젝트 개요
이 프로젝트는 **강아지 사진**을 업로드하고, 머신러닝 모델을 통해 해당 강아지의 **품종**을 **예측**하는 시스템입니다. <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=Streamlit&logoColor=white"/>, <img src="https://img.shields.io/badge/FastAPI-009688?style=flat&logo=FastAPI&logoColor=white"/>, <img src="https://img.shields.io/badge/Apache_Airflow-017CEE?style=flat&logo=Apache-Airflow&logoColor=white"/>, <img src="https://img.shields.io/badge/PySpark-E25A1C?style=flat&logo=Apache-Spark&logoColor=white"/>를 사용하여 이미지 업로드부터 **예측**, **집계**까지 **자동화**된 프로세스를 제공합니다. 또한, **관리자**는 이미지를 **직접 라벨링**할 수 있습니다.
<details>
  <summary><strong>예측 가능한 9종의 강아지 품종👈🏻</strong></summary>

  ![image](https://github.com/user-attachments/assets/1ef15084-3e1f-43c6-8612-b30e80ef475c)

</details>

## 🏗️ 아키텍처 개요
<details>
  <summary><strong>아키텍처 이미지 보기👈🏻</strong></summary>

  ![image](https://github.com/user-attachments/assets/02ea2818-bd7f-433e-abbf-4cda26aa7eb9)

</details>

## 🎯 주요 기능

1. **이미지 업로드 및 예측**
   - 사용자는 **Streamlit** 인터페이스를 통해 강아지 이미지를 업로드할 수 있습니다.
   - 업로드된 이미지는 **FastAPI**로 전송되어 데이터베이스에 저장됩니다.
   - 업로드된 이미지는 머신러닝 모델을 통해 강아지 품종을 예측합니다.
   - 예측 결과는 로그에 기록됩니다.

2. **관리자 페이지**
   - 관리자는 처리되지 않은 이미지를 확인하고 직접 라벨을 지정할 수 있습니다.
   - 각 이미지에 대한 라벨링 작업은 **Streamlit** 관리 페이지에서 수행됩니다.
   - 관리자는 라벨을 입력하고 제출하여 데이터베이스에 저장합니다.

3. **자동 예측 및 로그 기록**
   - **Airflow**를 사용하여 3분 마다  머신러닝 모델이 실행됩니다.
   - 각 실행 결과는 로그에 기록되어 데이터 분석에 활용됩니다.

4. **데이터 집계 및 분석**
   - **PySpark**를 활용하여 예측된 데이터를 집계하고 분석합니다.
   - 분석 결과는 데이터 기반 의사결정에 사용될 수 있습니다.

5. **사용자 친화적인 인터페이스**
   - **Streamlit**을 이용한 직관적인 사용자 인터페이스로 쉽게 이미지 업로드 및 라벨링 가능.
   - 관리자는 처리할 데이터가 없는 경우에도 쉽게 상태를 확인할 수 있습니다.

## 📋 시스템 구성 요소

- **사용자 인터페이스**: Streamlit
- **API 서버**: FastAPI
- **데이터베이스**: MySQL
- **작업 스케줄러**: Apache Airflow
- **데이터 처리 및 분석**: PySpark

## 🚀 사용 방법

### User Mode
1. Streamlit 접속(http://43.200.252.241:8501/)
2. app esther 접속
3. 강아지 이미지 업로드
<details>
  <summary><strong>업로드 화면 예시👈🏻</strong></summary>

  ![image](https://github.com/user-attachments/assets/024a9af0-61a6-4385-8bea-d159b3cae77a)

</details>   

### Manager Mode
1. Streamlit 접속(http://43.200.252.241:8501/)
2. manager page 접속
3. 강아지 이미지 라벨링
<details>
  <summary><strong>라벨링 화면 예시👈🏻</strong></summary>

  ![image](https://github.com/user-attachments/assets/614f71e9-fee3-4ea5-826b-5b92d3deda6d)

</details>


## 📄 라이센스
이 라이센스는 소프트웨어의 사용, 복사, 수정, 병합, 출판 및 판매를 허가하며, 소프트웨어의 저작권 및 라이센스 고지를 포함해야 합니다.

모델 출처: [dog-races](https://huggingface.co/roschmid/dog-races)
## 💬 문의

질문이나 제안사항이 있으면 언제든지 연락주세요🙋
```
- 이메일: nagazo@nagazo.com
- GitHub: EstherCho-7, DONGUK777, Kimwonjoon, mangG907 
```

![Footer](https://capsule-render.vercel.app/api?type=waving&color=87CEEB&height=200&section=footer)

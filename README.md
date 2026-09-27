# Capstone-Design-Alt-Text

캡스톤디자인2 프로젝트  
**이미지·문맥 정보를 활용한 한국어 웹 대체텍스트 품질 분석**

## VLM Alt Text Generation

크롤링한 마켓컬리 상품 이미지를 Vision-Language Model(VLM)에 입력하여
한국어 대체텍스트(alt text)를 생성하는 단계임.

딥러닝 모델 자체의 구조 분석보다는,
선행연구에서 비교된 VLM을 활용해 이미지 설명을 생성하고
이후 N-gram, TF-IDF 기반 텍스트 분석에 활용하는 것을 목적으로 함.

---

## Models

현재 다음 모델을 사용했음.

- Qwen2.5-VL-3B-Instruct
- HyperCLOVAX-SEED-Vision-Instruct-3B

동일한 이미지와 동일한 프롬프트를 사용해 모델별 대체텍스트를 생성했음.

---

## Dataset

마켓컬리 상품 페이지에서 수집한 이미지를 사용했음.

```text
bakery/
├─ images/
└─ bakery_metadata.csv

convenience_meals/
├─ images/
└─ convenience_meals_metadata.csv

fruits_nuts_rice/
├─ images/
└─ fruits_nuts_rice_metadata.csv

vegetables/
├─ images/
└─ vegetables_metadata.csv

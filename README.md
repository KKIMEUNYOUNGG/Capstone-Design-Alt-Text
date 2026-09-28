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

## 모델 및 담당자

| 담당자 | 실행 모델 | 결과 파일 |
|---|---|---|
| 은영 | Qwen2.5-VL-3B-Instruct, HyperCLOVAX-SEED-Vision-Instruct-3B | `alt_eunyoung.csv` |
| 서현 | BLIP-2, Qwen3-VL | `alt_seohyun.csv` |
| 해인 | BLIP, GIT, ViT-GPT2 | `alt_haein.csv` |

## 결과 파일 구성

각 담당자는 자신이 실행한 모든 모델의 생성 결과를 하나의 CSV 파일에 저장합니다.

- 파일명: `alt_자기이름.csv`
- 이미지 한 장당 한 행으로 구성
- 공통 정보 컬럼명은 노션에 정리된 기준으로 통일
- 실행한 모델별 대체텍스트를 각각 별도의 컬럼으로 추가
- 테스트 데이터가 아닌 전체 이미지 실행 결과 저장

예시:

| category | product_id | image_order | prev_alt_KOR | 모델 |
|---|---|---|---|---|

## 결과 통합

담당자별 CSV 파일을 동일한 이미지 식별자를 기준으로 병합하여 `alt_generate.csv`를 생성합니다. 최종 통합 파일에는 모든 모델의 대체텍스트 생성 결과가 각각의 컬럼으로 포함됩니다.

## 업로드 파일

- `alt_eunyoung.csv`
- `alt_seohyun.csv`
- `alt_haein.csv`
- `alt_generate.csv`

업로드 브랜치: [`vlm-alt-generation`](https://github.com/KKIMEUNYOUNGG/Capstone-Design-Alt-Text/tree/vlm-alt-generation)

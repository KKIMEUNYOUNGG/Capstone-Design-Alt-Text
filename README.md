## 캡션 오류 수정

### 1. 파일명 규칙

`카테고리_모델명_correct_담당자.xlsx`

- 카테고리: `bakery`, `convenience_meals`, `fruits_nuts_rice`, `vegetables`
- 모델명: `hyperclovax`, `qwen3` 등 사용 모델명
- 담당자: `은영`, `서현`, `해인`
- 수정 파일은 `data/` 폴더에 저장

**파일명 예시**
- `convenience_meals_hyperclovax_correct_key.xlsx`
- `fruits_nuts_rice_hyperclovax_correct_key.xlsx`
- `vegetables_hyperclovax_correct_key.xlsx`

### 2. 카테고리별 오류 수정 담당

| 카테고리 | 모델 | 담당 범위 | 담당자 |
|---|---|---|---|
| 간편식·밀키트·샐러드 | HyperCLOVAX | 전체 | 은영 |
| 과일·견과류·쌀 | HyperCLOVAX | 1~40번 (40개) | 해인 |
| 과일·견과류·쌀 | HyperCLOVAX | 41~70번 (30개) | 서현 |
| 과일·견과류·쌀 | HyperCLOVAX | 71~100번 (30개) | 은영 |
| 과일·견과류·쌀 | Qwen3 | 전체 | 서현 |
| 채소 | HyperCLOVAX | 1~40번 (40개) | 은영 |
| 채소 | HyperCLOVAX | 41~70번 (30개) | 서현 |
| 채소 | HyperCLOVAX | 71~100번 (30개) | 해인 |
| 베이커리 | Qwen3 | 전체 | 해인 |

### 3. 캡션 오류 수정 기준

- 이미지와 일치하지 않는 숫자, 수량, 상품명 수정
- 이미지에 존재하지 않는 객체나 특징을 설명한 경우 수정
- 이미지에서 실제 확인되는 주변부 설명은 유지
- 기존 생성 캡션은 변경하지 않고 바로 옆에 수정 컬럼 추가
- 오류가 있는 경우에만 수정된 전체 캡션 작성
- 수정할 필요가 없는 경우 수정 컬럼은 빈칸으로 유지

### 4. 저장 방법

- 원본 데이터 및 생성 캡션 유지
- 수정 파일은 `_correct_담당자.xlsx` 형식으로 별도 저장
- 각자 담당 구간만 수정하고, 다른 담당자의 구간은 변경하지 않음
- 최종 파일은 `keyword-caption-generation` 브랜치의 `data/` 폴더에 업로드

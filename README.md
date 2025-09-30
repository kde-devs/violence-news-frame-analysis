# violence-news-frame-analysis
Analysis of frames in violence-related news articles

---

## 팀 정보
- **팀장**: [금다은](https://github.com/kde-devs)
- **팀원**: [허다인](https://github.com/dainheo), [윤하늘](https://github.com/gksmfoi)

---

## 프로젝트 배경
> 이 프로젝트는 2025년도 2학기 데이터사이언스 전공 수업인 ‘텍스트 데이터 분석’을 기반으로 시작되었습니다.  
본 프로젝트는 뉴스 기사에서 **폭력 사건 관련 보도**가 어떤 프레임(Frame)을 갖는지 분석하는 것을 목표로 합니다.  
이를 통해 언론의 보도 경향과 사회적 편향을 이해하고 시각화합니다.
---

## 데이터
- **수집 대상**: 국내외 뉴스 기사 (폭력 관련)
- **형식**: CSV / JSON
- **주요 컬럼**
  - `title`: 기사 제목
  - `content`: 기사 본문
  - `date`: 발행일
  - `source`: 뉴스 출처
  - `frame`: 기사 프레임 레이블 (수동 또는 모델 기반)

## 분석 방법
1. **데이터 전처리**
   - 불용어 제거, 토큰화, 정규화
   - 핵심 문장 추출
2. **프레임 분류**
   - 예시 프레임: `공격적`, `방어적`, `중립적`, `피해자 중심`, `가해자 중심`
   - 모델: TF-IDF + Logistic Regression / BERT 기반 분류
3. **시각화 및 인사이트**
   - 프레임별 기사 비율
   - 시간/출처별 프레임 변화
   - 상관관계 분석

## 사용 기술
- Python 3.10
- 라이브러리: pandas, scikit-learn, transformers, matplotlib, seaborn
- 데이터 수집: BeautifulSoup, requests

## 설치 및 실행 방법
```bash
# 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows

# 필요 라이브러리 설치
pip install -r requirements.txt

# 데이터 전처리 및 분석 실행
python preprocess.py
python analyze.py
python visualize.py

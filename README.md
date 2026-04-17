# MS_Crawling

> Web Crawler · Scraping · Open API 데이터 수집 실습 저장소

---

## 개요

본 저장소는 **BeautifulSoup**, **Selenium**, **공공 Open API** 등을 활용하여 다양한 방식의 웹 데이터 수집 기술을 단계적으로 실습한 결과물을 담고 있습니다.  
정적 페이지 크롤링부터 동적 SPA 페이지, 무한 스크롤, API 호출까지 실무에서 자주 사용하는 데이터 수집 기법 전반을 다룹니다.

---

## 저장소 구조

```
MS_Crawling/
├── 01_정적웹페이지 데이터 수집_실습.ipynb     # 정적 HTML 파싱 실습
├── 01_정적웹페이지 데이터 수집_완성.ipynb     # 정적 HTML 파싱 완성본
├── 02_네이버증권뉴스_실습.ipynb               # 네이버 증권 뉴스 크롤링 실습
├── 02_네이버증권뉴스_완성.ipynb               # 네이버 증권 뉴스 크롤링 완성본
├── 03_동적웹페이지 데이터수집_실습.ipynb      # Selenium 동적 페이지 수집 실습
├── 03_동적웹페이지 데이터수집_완성.ipynb      # Selenium 동적 페이지 수집 완성본
├── 04_뉴스댓글1_sleep_실습.ipynb              # sleep 기반 대기 전략 실습
├── 04_뉴스댓글1_sleep_완성.ipynb              # sleep 기반 대기 전략 완성본
├── 04_뉴스댓글2_명시적대기_실습.ipynb         # WebDriverWait 명시적 대기 실습
├── 04_뉴스댓글2_명시적대기_완성.ipynb         # WebDriverWait 명시적 대기 완성본
├── 05_무한스크롤_실습.ipynb                   # 무한 스크롤 처리 실습
├── 05_무한스크롤_완성.ipynb                   # 무한 스크롤 처리 완성본
├── 06_셀렉트박스_실습.ipynb                   # Select 태그 자동화 실습
├── 06_셀렉트박스_완성.ipynb                   # Select 태그 자동화 완성본
├── 07_opneAPI_공공데이터_문화축제_실습.ipynb  # 공공 Open API 호출 실습
├── 07_opneAPI_공공데이터_문화축제_완성.ipynb  # 공공 Open API 호출 완성본
├── 08_yes24_베스트셀러_실습.ipynb             # Yes24 베스트셀러 수집 실습
├── 08_yes24_베스트셀러_완성.ipynb             # Yes24 베스트셀러 수집 완성본
├── 09_워드클라우드시각화_실습.ipynb            # 수집 데이터 워드클라우드 실습
├── 09_워드클라우드시각화_완성.ipynb            # 수집 데이터 워드클라우드 완성본
└── data/                                      # 수집된 데이터 저장 폴더
```

---

## 주요 구현 내용

### 01. 정적 웹페이지 데이터 수집
- **라이브러리**: `requests`, `BeautifulSoup4`
- HTML 응답 파싱, CSS 선택자 및 find/find_all 활용
- 태그·속성·텍스트 추출 및 데이터 구조화

### 02. 네이버 증권 뉴스 크롤링
- 네이버 증권 뉴스 목록 페이지 순회 크롤링
- 뉴스 제목, URL, 날짜 등 메타데이터 수집 및 CSV 저장
- 페이지 파라미터 변경을 통한 다중 페이지 수집

### 03. 동적 웹페이지 데이터 수집
- **라이브러리**: `Selenium`, `ChromeDriver`
- JavaScript 렌더링 이후 생성되는 동적 콘텐츠 수집
- 브라우저 자동화를 통한 SPA(Single Page Application) 대응

### 04. 뉴스 댓글 수집 (대기 전략 비교)
- **방법 1 — sleep 기반 고정 대기** (`time.sleep`): 단순하지만 비효율적
- **방법 2 — 명시적 대기** (`WebDriverWait` + `ExpectedConditions`): 요소 등장 조건 기반의 효율적 대기
- 두 방식의 안정성·성능 비교 실습

### 05. 무한 스크롤 처리
- `window.scrollTo` JavaScript 실행으로 스크롤 이벤트 트리거
- 스크롤 후 새 콘텐츠 로딩 대기 및 반복 수집 자동화
- 스크롤 종료 조건 판별 로직 구현

### 06. 셀렉트박스 자동화
- Selenium `Select` 클래스를 통한 드롭다운 메뉴 제어
- 옵션 목록 순회 및 각 옵션별 데이터 수집 자동화

### 07. 공공 Open API 활용 (문화축제)
- **공공데이터포털** API 키 발급 및 호출
- JSON 응답 파싱 및 DataFrame 변환
- 문화 축제 행사 정보 (이름, 날짜, 장소 등) 수집 및 저장

### 08. Yes24 베스트셀러 수집
- Yes24 베스트셀러 랭킹 페이지 크롤링
- 책 제목, 저자, 순위, 가격 등 정보 추출
- 카테고리별 다중 페이지 수집 자동화

### 09. 워드클라우드 시각화
- 수집한 텍스트 데이터 전처리 (형태소 분석, 불용어 제거)
- `WordCloud`, `matplotlib` 라이브러리를 활용한 시각화
- 수집 데이터의 주요 키워드 빈도 시각적 표현

---

## 사용 기술

| 분류 | 기술 |
|------|------|
| 언어 | Python 3.x |
| 정적 크롤링 | requests, BeautifulSoup4 |
| 동적 크롤링 | Selenium, ChromeDriver |
| 데이터 처리 | Pandas |
| API 호출 | requests (JSON/XML 파싱) |
| 시각화 | WordCloud, matplotlib, KoNLPy (형태소 분석) |
| 개발 환경 | Jupyter Notebook |

---

## 실행 방법

```bash
# 가상 환경 활성화 (프로젝트 내 .venv 포함)
source .venv/bin/activate  # Linux/Mac
.venv\Scripts\activate      # Windows

# Jupyter Notebook 실행
jupyter notebook

# 특정 노트북 바로 실행
jupyter notebook 01_정적웹페이지\ 데이터\ 수집_완성.ipynb
```

> Selenium 사용 시 Chrome 버전에 맞는 ChromeDriver가 필요합니다.

---

## 학습 목표 달성 사항

- [x] requests + BeautifulSoup을 활용한 정적 웹페이지 데이터 수집
- [x] Selenium을 활용한 동적 웹페이지 및 JavaScript 렌더링 페이지 수집
- [x] 공공데이터포털 Open API 호출 및 JSON 데이터 파싱
- [x] 무한 스크롤, 셀렉트박스 등 고급 웹 자동화 기법 구현
- [x] 수집 데이터 전처리 및 워드클라우드 시각화

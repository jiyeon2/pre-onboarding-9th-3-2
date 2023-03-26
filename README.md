# 시계열 차트

JSON 데이터를 시계열 차트로 표시


## 배포 링크 🔗

[https://keen-lily-5dbf2f.netlify.app/](https://keen-lily-5dbf2f.netlify.app/)

## 실행 방법 👟

```
yarn install
yarn dev

&&

npm install
npm run dev

```

## 디렉토리 구조 📂

```
📦src
 ┣ 📂api
 ┃ ┗ 📜httpClient.ts
 ┣ 📂components
 ┃ ┣ 📜FilterButtons.tsx
 ┃ ┗ 📜TimeSeriesChart.tsx
 ┣ 📂consts
 ┃ ┗ 📜chart.const.ts
 ┣ 📂hooks
 ┃ ┣ 📜useData.tsx
 ┃ ┗ 📜useFilterQueryString.tsx
 ┣ 📂types
 ┃ ┣ 📜chartData.types.ts
 ┃ ┗ 📜response.types.ts
 ┣ 📂utils
 ┃ ┣ 📜getChartData.ts
 ┃ ┣ 📜getChartOption.ts
 ┃ ┣ 📜getDatasetStyleByFilter.ts
 ┃ ┣ 📜getUniqueLocations.ts
 ┃ ┗ 📜registChartJS.ts
 ┣ 📜App.css
 ┣ 📜App.tsx
 ┣ 📜index.css
 ┣ 📜main.tsx
 ┗ 📜vite-env.d.ts
```

## 사용 기술 스택 🔨

| 사용처 | 사용 기술 | 결정 사유 |
| --- | --- | --- |
| 프레임워크 | React (Vite) | - CRA와 비교했을 때 매우 효율적으로 번들링 작업 진행 |
| 언어 | Typescript(Javascript) | - 더 안정적인 코드 작성: 컴파일 과정에서 버그를 사전에 찾을 수 있음 <br /> - 개발 생산성 향상: 자동완성, 타입체크, 에러 표시 도구 제공 <br /> - 코드 가독성 향상: 개발자가 코드를 이해하고 유지보수하기 쉽게 만듦 |
| 라우팅 처리 | react-router-dom | params를 이용한 필터링 적용 |
| 차트 라이브러리 | Chart.js (react-chartjs-2 ) | - 인기 많은 차트 라이브러리 <br /> - 작은 번들 사이즈 <br />- canvas 기반으로 DOM에 부담 적음 <br /> - TS로 작성되어 있음|
| 코드 포매팅 | ESLint |  |
| 배포 | netlify | - Github 레포지토리와 연동하여 배포 |

## 주안점 💫

- 관심사 분리
    - 차트 데이터 불러오기는 커스텀 훅에서, 렌더링은 컴포넌트에서 처리
    - chartjs 에서 필요한 config 값을 options / dataset으로 분리하여 파일 만듦
- 상수를 분리하여 여러 코드에서 동일한 문자열을 키값으로 사용
- 필터링 적용 : url querystring 활용

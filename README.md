# AMRED HEALTHCARE BACKOFFICE
## 목차

1. [프로젝트 개요](#1-프로젝트-개요)

2. [프로젝트 범위](#2-프로젝트-범위)

3. [폴더 구조](#3-폴더-구조)

4. [기술 스택](#4-기술-스택)

<br>

## 1. 프로젝트 개요

본 프로젝트는 AMRED의 헬스케어 서비스 WIM-DIET의 백오피스로 유저는 WIM매니저, 일반 관리자, 슈퍼 관리자로 구분됩니다. <br>
프론트 오피스를 통해 회원들이 기록한 영양 및 생활 관련 데이터를 기반으로 효율적인 관리 서비스를 제공하며, 사용자들의 건강한 라이프스타일 개선을 지원합니다.

<br>

## 2. 프로젝트 범위

> ### 로그인

- 유저는 WIM매니저/일반관리자/슈퍼관리자로 구분되며, 유저별로 주어지는 권한이 상이합니다.

- 로컬스토리지에 토큰 및 필수 정보를 저장합니다.

![로그인](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/a15779d0-dca6-4c35-9d9a-39655f7e16cc)

<br>

> ### 식단

- 식단과 메뉴를 생성하고 수정할 수 있습니다.

- 모든 유저의 접근이 가능합니다.
  
![식단](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/c1321052-f171-4800-b111-45f17c76673a)

<br>

> ### 회원 리스트

- 회원 관리 페이지로, 회원 계정 생성 및 정보 수정, 삭제가 가능합니다.

- 리스트에서 이름,성별,나이 등을 기반으로 검색 필터링이 가능합니다.

- 모든 유저의 접근이 가능합니다.

![회원 리스트](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/eb6d8aca-602c-4763-be0a-d30d53054d69)

- 담당자 필터
  - 검색 및 해당 담당자를 선택하면, 해당 담당자가 담당하고 있는 회원들만 필터링됩니다.

![담당자 필터](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/2af08676-38a7-4bd8-8e74-0d0df3f74109)

<br>

> ### WIM매니저 리스트

- WIM매니저 관리 페이지로, WIM 매니저 계정 생성 및 정보 수정, 삭제가 가능합니다.

- 일반 관리자와 슈퍼관리자만 접근이 가능합니다.

![WIM매니저 리스트](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/32ca1f05-502a-4f9d-9db3-9984a022f489)

<br>

> ### 관리자 리스트

- 일반 관리자 관리 페이지로, 일반 관리자 계정 생성 및 정보 수정, 삭제가 가능합니다.

- 슈퍼 관리자만 접근이 가능합니다.

![관리자 리스트](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/95b6104a-20cd-49b0-998b-37250a4866ba)

<br>

> ### 회원 대시보드

- 프론트오피스에서 회원이 기록한 데이터를 종합적으로 확인할 수 있는 페이지입니다. 

- 일별 체중 변화 추이를 시각화하여 제공합니다.

- 월별 수면시간, 수분, 체중 등을 캘린더 형태로 제공합니다.

- WIMbody, WIM분석, 미션, WIM가이드, 그리고 TCI를 회원별로 맞춤형으로 제공 가능합니다.

![회원 대시보드](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/3f838dcd-f096-4fcf-b4b9-55d0748c04e4)

<br>

> ### 회원 일별 레코드

- 캘린더에서 날짜 클릭 시 전환되는 페이지로, 회원이 기록한 생활 데이터를 자세히 확인할 수 있습니다.

- 담당 WIM매니저 및 관리자가 식단(아침/점심/저녁/간식)에 대한 코멘트를 작성/수정 할 수 있습니다.

![회원 일별레코드](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/f1aa46c4-8607-41b3-b8be-af68de0aa929)

<br>

> ### 회원 메모

- 일반 메모와 관리 메모로 구성됩니다.

- 일반 메모는 텍스트 컨텐츠만 작성 가능합니다.

- 관리 메모 기능은 텍스트 컨텐츠와 이미지 업로드가 가능하며, 이미지 업로드에는 Presigned URL 방식을 사용하였습니다.

![메모](https://github.com/eunrain/amred-backoffice-frontend/assets/113877276/17c5edc7-13cc-44b3-95e1-55d1f1b1c4bb)

<br>

## 3. 폴더 구조
```
apis
 - apiClient.ts
 - auth.ts
 - clinic.ts
 - fileManage.ts
 - records.ts
 - user.ts

components
 ㄴ📁 form
   - AccountForm.tsx
   - ClientForm.tsx
   - LoginForm.tsx
   - NutritionistForm.tsx
   - WIMAnalysisForm.tsx
   - WIMClinicForm.tsx

 ㄴ📁global
   - Button.tsx
   - Layout.tsx
   - PrimaryButton.tsx
   - Sidebar.tsx
   - Title.tsx

 ㄴ📁member-dashboard
   - CustomCalendar.tsx
   - DataTable.tsx
   - MemberInfo.tsx
   - TCI.tsx
   - WeightChart.tsx

 ㄴ📁member-memo
   - EditMemoModal.tsx
   - MemoModal.tsx
   - MemoTable.tsx

 ㄴ📁member-record
   - CarouselSlider.tsx
   - RecordContainer.tsx
   - RecordDietList.tsx

 ㄴ📁menu
   - MenuList.tsx

 ㄴ📁modal
   - ClickModal.tsx
   - FormModal.tsx
   - MenuModal.tsx
   - SelectModal.tsx

 ㄴ📁table
   - ManagerModal.tsx
   - Table.tsx

hooks
 - useForm.ts
 - useModal.ts
 - useOnClickOutside.ts

pages
 - _app.tsx
 - _document.tsx
 - admin.tsx
 - index.tsx
 - login.tsx
 - member-dashboard.tsx
 - member-memo.tsx
 - member-record.tsx
 - member.tsx
 - menu.tsx
 - nutritionist.tsx

styles
 - globals.css

types
 - type.d.ts

utils
 - calculateAge.ts
 - getFileExtension.ts
 - getFormatDate.ts
 - getStorage.ts
```

<br>

## 4. 기술 스택

|     언어     |   버전 |
| :----------: | :----: |
|   Typescript | 5.1.6  |

| 프레임워크 |   버전   |
| :--------: | :------: |
|    NextJs  | 13.4.12  |

|     라이브러리     |    버전   |
| :----------------: | :-------: |
|        react       |   18.2.0  |
|     react-query    |   3.39.3  |
|     tailwindcss    |   3.3.3   |
|   react-datepicker |   4.16.0  |
|     react-table    |  7.8.0    |
|       recharts     |   2.7.2   |


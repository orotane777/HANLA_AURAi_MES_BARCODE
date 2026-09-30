# 현장 작업기록 데모

폰으로 작업 요청서의 바코드나 QR을 찍어 작업 시간을 기록하는 웹앱 데모다. 화면과 동작을 확인하기 위한 시안이며, 데모 데이터로만 동작한다.

- 앱: https://orotane777.github.io/HANLA_AURAi_MES_BARCODE/
- 데모 바코드: https://orotane777.github.io/HANLA_AURAi_MES_BARCODE/barcodes.html

## 무엇을 하나

작업자의 하루를 세 가지 활동으로 기록한다.

| 활동 | 시작 방법 |
|---|---|
| 호선작업 | 요청서 바코드 스캔 |
| 생산지원 | 요청서 바코드 스캔 |
| 생산외 | 목록에서 선택 (청소·정리, 조례·회의, 안전·직무교육, 설비 점검·수리) |

다음 활동을 시작하면 이전 기록이 자동으로 닫힌다. 일시정지는 없다. 하루 끝에만 종료를 누르면 된다.

그 밖에 메모, 상세(기록 정보와 오늘 활동별 누적 시간), 라이트·다크 테마가 있다.

## 써보는 법

1. PC 모니터에 [데모 바코드](https://orotane777.github.io/HANLA_AURAi_MES_BARCODE/barcodes.html)를 띄운다
2. 폰에서 [앱](https://orotane777.github.io/HANLA_AURAi_MES_BARCODE/)을 열고 카메라 권한을 허용한다
3. 모니터의 바코드를 사각틀 안에 맞춘다. 인식되면 기록이 시작된다
4. 다른 작업을 찍으려면 가운데 어두워진 원 버튼을 다시 누른다
5. QR을 찍을 때는 사각틀 위의 QR 버튼으로 바꾼다

바코드가 없으면 사각틀을 손가락으로 눌러도 데모 작업이 차례로 시작된다.

## 지원 환경

- 안드로이드 크롬 — 브라우저에 내장된 바코드 인식기를 쓴다
- 아이폰 사파리 (iOS 15.4 이상) — 내장 인식기가 없어 라이브러리를 불러와 쓴다

카메라는 HTTPS에서만 열린다. 파일을 폰에 복사해서 열거나 `http://` 주소로 열면 카메라가 동작하지 않는다.

## 파일

- `index.html` — 앱 전체. HTML·CSS·JavaScript가 한 파일에 있다
- `barcodes.html` — 데모 바코드 시트

빌드 과정이 없다. 수정한 파일을 그대로 올리면 GitHub Pages에 반영된다.

## 로컬에서 띄우기

카메라는 `localhost`에서도 열린다. 폴더에서 아래 명령을 실행하고 PC 브라우저로 `http://localhost:8000`을 연다.

```bash
python -m http.server 8000
```

## 사용한 것

| 용도 | 라이브러리 |
|---|---|
| 바코드 인식 (내장 인식기가 없는 브라우저) | [barcode-detector](https://github.com/Sec-ant/barcode-detector) 2.x |
| 바코드 그리기 | [JsBarcode](https://github.com/lindell/JsBarcode) 3.11.6 |
| QR 그리기 | [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) 1.4.4 |
| 글꼴 | [SUIT](https://github.com/sun-typeface/SUIT) (SIL Open Font License) |

모두 CDN으로 불러오며 이 저장소에 포함하지 않았다.

## 데이터

데모 바코드의 번호, 호선, 품명은 모두 가짜다. 기록은 서버로 보내지 않고 이 기기의 브라우저 저장소에만 남는다. 날짜가 바뀌면 지운다.

# 24개 지역 지방의회 공식 기록·의원 안내

제작: [잘하나(JALHANA)](https://jalhana.com/) · **[대표 안내·웹 목록](https://jalhana.com/resources/local-councils/)**

**v0.2.6 · 자료 기준일 2026-10-04 · 24개 지역 베타**

첫 공개일 2026-10-04 · 이번 버전 갱신일 2026-10-05. 링크별 확인일은 데이터의 `checked_at`에 따로 기록합니다.

지방의회의 공식 홈페이지와 회의록·의안·의원 안내 진입 경로를 찾고 재사용할 수 있도록 정리한 자료입니다.
24개 지역의 96개 링크와 URL별 출처·확인 기록을 제공합니다.
JSON의 `null`은 CSV의 빈 칸과 같습니다. CSV는 엑셀에서 한글을 바로 읽도록 UTF-8 BOM을 포함합니다. Python에서는 `encoding="utf-8-sig"`로 읽습니다.

## 바로 사용하기

- [잘하나 웹 목록](https://jalhana.com/resources/local-councils/): 기관별 공식 링크와 확인 범위를 읽습니다.
- [JSON](data/councils.json) / [CSV](data/councils.csv): 동일한 24행·31필드, UTF-8입니다.
- [필드 설명](docs/fields.md) / [JSON Schema](schema/councils.schema.json) / [방법론](docs/methodology.md)
- [릴리스 정보](release.json) / [파일 해시](manifest.sha256) / [변경 이력](CHANGELOG.md)

```python
import json
with open("data/councils.json", encoding="utf-8") as source:
    councils = json.load(source)
for council in councils:
    print(council["council_name"], council["minutes_url"])
```

공식 메뉴 관찰, 직접 HTTP 응답 확인, 이용자의 직접 접속 확인을 각각
`navigation_observed`, `http_response_checked`, `user_confirmed`로 기록합니다.
`scope`는 최근회의록·의안검색 등 링크의 용도를 설명합니다.

## 권장 인용

> 잘하나(JALHANA), 「24개 지역 지방의회 공식 기록·의원 안내」, v0.2.6 (2026-10-05), 자료 기준일 2026-10-04, https://jalhana.com/resources/local-councils/

기계 판독용 인용 정보: [CITATION.cff](CITATION.cff). [이 버전의 고정 파일](https://github.com/lime38/local-council-public-records/tree/v0.2.6).
개별 기관의 공식 기록을 이용한 글에는 해당 기록의 원출처도 함께 표시해 주세요.
변경·재구성한 경우 변경 내용을 밝혀 주세요. 특정 링크 속성이나 앵커 문구를 요구하지 않습니다.

## 이용 범위

잘하나의 자체 작성 메타데이터와 설명 문서는 보유 권리 범위에서 **CC BY 4.0**으로 제공합니다.
기관명·URL 같은 사실 자체에 새로운 권리를 주장하지 않습니다.
정부·의회의 원문 회의록, 의안 본문, 첨부 자료, 기관 로고·사진 등은 배포물에 포함하지 않으며
이 라이선스의 적용 대상도 아닙니다. 원자료의 권리와 이용조건은 각 제공기관·권리자의 안내를 따릅니다.
자세한 적용 범위는 [LICENSE](LICENSE)와 [DATA_POLICY.md](DATA_POLICY.md)에 있습니다.

## 정정 제안

[공개 이슈](https://github.com/lime38/local-council-public-records/issues)에 기관명·항목·공식 출처 URL·확인 날짜와 제안 내용을 알려 주세요.
개인정보, 로그인 정보, 비공개 문서, 원문 전체 파일은 첨부하지 말아 주세요.
확인된 정정은 새 버전과 변경 이력에 반영합니다.

공개 웹과 파일은 같은 버전으로 제공합니다. [잘하나 공개 리소스 허브](https://jalhana.com/resources/)에서
설명을 읽고, [이 저장소](https://github.com/lime38/local-council-public-records)에서 파일과 변경 이력을 확인할 수 있습니다.

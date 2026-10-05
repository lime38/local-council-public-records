# 필드 설명

JSON은 기관별 객체 56개를 담은 배열이며 CSV는 같은 순서의 필드를 갖습니다.
모든 값은 문자열 또는 `null`입니다. CSV의 빈 칸은 JSON `null`과 동일하며 빈 문자열 자체는 사용하지 않습니다.
CSV는 UTF-8, 쉼표 구분, CRLF 행 종결입니다. 쉼표·따옴표는 표준 CSV 인용 규칙으로 보존합니다.
수식 시작 문자(`=`, `+`, `-`, `@`)와 제어 문자로 시작하거나 이를 포함하는 위험한 입력은 생성 전에 거부합니다.
스키마 외에 생성기가 명시된 지역 입력·중복·확인 기록의 필드 관계를 검사합니다.

| 필드 | 의미 |
|---|---|
| `release_version` | 공개 릴리스 버전 (release.json과 같음) |
| `scope_as_of` | 이 릴리스의 자료 기준일(YYYY-MM-DD); 개별 접속 확인일과 다름 |
| `council_id` | 이 리소스의 안정적인 문자열 ID; 공식 행정코드가 아님 |
| `region` | 대상 지역 |
| `council_name` | 기관 명칭 |
| `council_level` | 기관 구분: 광역 또는 기초; 의원별 정보가 아님 |
| `homepage_url` | 공식 홈페이지: 공식 접근 URL; 알 수 없으면 null |
| `homepage_source_url` | 공식 홈페이지: 공식 메뉴 또는 직접 접속 확인을 받은 공식 URL |
| `homepage_checked_at` | 공식 홈페이지: 관찰·확인 기록 시각(시간대 포함 ISO 8601); user_confirmed는 사용자 확인 보고를 기록한 시각 |
| `homepage_method` | 공식 홈페이지: 실제로 수행한 확인 방법 |
| `homepage_status` | 공식 홈페이지: navigation_observed / http_response_checked / user_confirmed / unknown |
| `homepage_scope` | 공식 홈페이지: 링크의 용도와 대상 기간 |
| `minutes_url` | 회의록: 공식 접근 URL; 알 수 없으면 null |
| `minutes_source_url` | 회의록: 공식 메뉴 또는 직접 접속 확인을 받은 공식 URL |
| `minutes_checked_at` | 회의록: 관찰·확인 기록 시각(시간대 포함 ISO 8601); user_confirmed는 사용자 확인 보고를 기록한 시각 |
| `minutes_method` | 회의록: 실제로 수행한 확인 방법 |
| `minutes_status` | 회의록: navigation_observed / http_response_checked / user_confirmed / unknown |
| `minutes_scope` | 회의록: 링크의 용도와 대상 기간 |
| `bills_url` | 의안: 공식 접근 URL; 알 수 없으면 null |
| `bills_source_url` | 의안: 공식 메뉴 또는 직접 접속 확인을 받은 공식 URL |
| `bills_checked_at` | 의안: 관찰·확인 기록 시각(시간대 포함 ISO 8601); user_confirmed는 사용자 확인 보고를 기록한 시각 |
| `bills_method` | 의안: 실제로 수행한 확인 방법 |
| `bills_status` | 의안: navigation_observed / http_response_checked / user_confirmed / unknown |
| `bills_scope` | 의안: 링크의 용도와 대상 기간 |
| `members_url` | 의원 안내: 공식 접근 URL; 알 수 없으면 null |
| `members_source_url` | 의원 안내: 공식 메뉴 또는 직접 접속 확인을 받은 공식 URL |
| `members_checked_at` | 의원 안내: 관찰·확인 기록 시각(시간대 포함 ISO 8601); user_confirmed는 사용자 확인 보고를 기록한 시각 |
| `members_method` | 의원 안내: 실제로 수행한 확인 방법 |
| `members_status` | 의원 안내: navigation_observed / http_response_checked / user_confirmed / unknown |
| `members_scope` | 의원 안내: 링크의 용도와 대상 기간 |
| `notes` | 기관·접근 범위의 추가 설명; 미확인은 null |

`navigation_observed`: 공식 메뉴·페이지에서 연결 주소를 관찰한 기록입니다.
`http_response_checked`: 직접 HTTP 응답을 확인한 기록입니다.
`user_confirmed`: 사용자가 직접 접속해 확인했다고 전달한 기록입니다. checked_at은 보고를 기록한 시각입니다.
`unknown`: 확인 기록이 없는 경우 사용하는 값입니다.

# 필드 설명

JSON은 기관별 객체 5개를 담은 배열이며 CSV는 같은 순서의 필드를 갖습니다.
모든 값은 문자열 또는 `null`입니다. CSV의 빈 칸은 JSON `null`과 동일하며 빈 문자열 자체는 사용하지 않습니다.
CSV는 UTF-8, 쉼표 구분, CRLF 행 종결입니다. 쉼표·따옴표는 표준 CSV 인용 규칙으로 보존합니다.
수식 시작 문자(`=`, `+`, `-`, `@`)와 제어 문자로 시작하거나 이를 포함하는 위험한 입력은 생성 전에 거부합니다.
스키마 외에 생성기가 고정 기관 집합·중복·확인 기록의 필드 관계를 검사합니다.

| 필드 | 의미 |
|---|---|
| `release_version` | 공개 릴리스 버전 0.1.0 |
| `scope_as_of` | 이 릴리스의 자료 기준일(YYYY-MM-DD); 개별 접속 확인일과 다름 |
| `council_id` | 이 리소스의 안정적인 문자열 ID; 공식 행정코드가 아님 |
| `region` | 대상 지역 |
| `council_name` | 기관 명칭 |
| `homepage_url` | 공식 홈페이지: 공식 접근 URL; 미확인은 null |
| `homepage_source_url` | 공식 홈페이지: 기관·메뉴·용도를 확인한 공식 출처 URL |
| `homepage_checked_at` | 공식 홈페이지: 관찰·확인 시각(시간대 포함 ISO 8601); 미확인은 null |
| `homepage_method` | 공식 홈페이지: 실제로 수행한 확인 방법 |
| `homepage_status` | 공식 홈페이지: navigation_observed / http_response_checked / unknown |
| `homepage_scope` | 공식 홈페이지: 확인한 용도·기간과 확인하지 않은 범위 |
| `minutes_url` | 회의록: 공식 접근 URL; 미확인은 null |
| `minutes_source_url` | 회의록: 기관·메뉴·용도를 확인한 공식 출처 URL |
| `minutes_checked_at` | 회의록: 관찰·확인 시각(시간대 포함 ISO 8601); 미확인은 null |
| `minutes_method` | 회의록: 실제로 수행한 확인 방법 |
| `minutes_status` | 회의록: navigation_observed / http_response_checked / unknown |
| `minutes_scope` | 회의록: 확인한 용도·기간과 확인하지 않은 범위 |
| `bills_url` | 의안: 공식 접근 URL; 미확인은 null |
| `bills_source_url` | 의안: 기관·메뉴·용도를 확인한 공식 출처 URL |
| `bills_checked_at` | 의안: 관찰·확인 시각(시간대 포함 ISO 8601); 미확인은 null |
| `bills_method` | 의안: 실제로 수행한 확인 방법 |
| `bills_status` | 의안: navigation_observed / http_response_checked / unknown |
| `bills_scope` | 의안: 확인한 용도·기간과 확인하지 않은 범위 |
| `notes` | 기관·접근 범위의 추가 설명; 미확인은 null |

`navigation_observed`: 공식 메뉴·페이지 내용을 관찰했습니다. 도구의 캐시 응답일 수 있습니다.
`http_response_checked`: 기록된 시각에 직접 HTTP 응답을 확인했습니다. 기능 전체의 작동 검증은 아닙니다.
`unknown`: 확인 상태를 확정하지 못했습니다. 해당 기능이나 자료가 없다는 뜻이 아닙니다.
모든 상태에서 `scope`와 `method`를 함께 읽어야 합니다.

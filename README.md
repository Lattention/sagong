# 사공 (Sagong)

Concept2 PM5 로잉머신에 연결해서 즐기는 1인칭 사공 게임 프로토타입입니다.

**플레이:** https://lattention.github.io/sagong/

- PC, 안드로이드: 크롬에서 위 주소를 엽니다.
- 아이폰: 사파리와 크롬은 블루투스 연결을 지원하지 않습니다. 앱스토어에서 **Bluefy** 브라우저를 설치하고 그 안에서 위 주소를 엽니다.
- PM5가 없으면 화면의 "노 젓기" 버튼이나 스페이스바로 저을 수 있습니다.

## 모드

- **해적 추격:** 해적선에게 따라잡히기 전에 500m 앞 항구로 들어갑니다.

## 내 모드 만들기

메뉴의 "내 모드 추가하기"에 JSON 설정을 붙여 넣으면 새 모드가 생깁니다.

```json
{
  "id": "my-night-escape",
  "name": "한밤의 탈출",
  "tagline": "달빛 아래 800m. 바위가 많다.",
  "look": { "sky": "#0d1b33", "horizon": "#3b4a6b", "sea": "#0f2f3d" },
  "goal": { "distance": 800, "label": "등대" },
  "pursuer": { "gap": 120, "speed": [2.4, 3.2], "ramp": 240, "label": "추격선" },
  "cannon": { "every": [8, 14] },
  "rocks": [{ "at": 150, "x": 4, "r": 3 }],
  "lines": [{ "at": 0, "say": "불을 끄고 조용히 저어라." }]
}
```

| 항목 | 뜻 |
| --- | --- |
| `goal.distance` | 목표까지 거리(m) |
| `pursuer.gap` / `speed` / `ramp` | 추격선의 처음 거리(m), 처음과 끝 속도(m/s), 끝 속도에 이르는 시간(초) |
| `cannon.every` | 포격 간격(초)의 최소, 최대 |
| `rocks` | 바위 위치. `at`은 출발점부터의 거리, `x`는 좌우, `r`은 크기 |
| `pace.segments` | 구령 구간. `at`부터 `target`(m/s) 속도를 `tol` 오차 안에서 유지, `spm`은 북 박자 |
| `lines` | 특정 거리에서 나오는 대사 |
| `steer` | `false`면 방향타 없음 |
| `boat` | `skiff` 또는 `turtle` |

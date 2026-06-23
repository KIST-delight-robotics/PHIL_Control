# Change Log

## 2026-06-22
- 10:42 KST (UTC+9) — head 제스처(nod/wave/hurray) tilt 숫자를 연주/planner와 같은 관례로 정정
  - 수정 파일: `src/AgentAction.cpp`
  - 메모: head_tilt 관례는 정면 90, 위 70, 아래 110 (연주 경로 `makeNod`/readyAngle(13)=110 및 phil_robot planner `LOOK_UP=70`/`LOOK_DOWN=110`가 ground truth). `policy_gesture`의 하드코딩 tilt가 반대 가정(70=아래,110=위)으로 적혀 있어 연주와 반대로 움직였다. `policy_lookAt`은 공용 경로라 변환을 넣지 않고(planner의 `look:` 숫자가 이미 올바름), 하드코딩 숫자만 90° 기준 반사: nod 70↔110, wave 95→85, hurray 105→75. shake는 tilt 90이라 불변.

## 2026-06-16
- 15:00 KST (UTC+9) — 레포 분할 준비: 인터페이스 계약 단일 소스와 분리-레포용 에이전트 지침 추가
  - 수정 파일: 신규 `CONTRACTS.md`, `AGENTS.md`
  - 메모: 이 레포(`phil-controller`)의 독립 로그를 0에서 시작. 이전 통합 로그는 옮기지 않는다.

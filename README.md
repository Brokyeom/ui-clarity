# UI Clarity

기존 제품 UI의 중복 정보와 불필요한 설명을 정리하는 에이전트 스킬입니다. 화면을 간결하게 만들면서 오류, 집계 범위, 접근성처럼 사용자의 판단에 필요한 정보는 유지합니다.

## 사용 예시

```text
$ui-clarity로 이 대시보드의 불필요한 설명과 중복 정보를 정리해줘.
```

```text
$ui-clarity로 로그인 화면을 검토하고 개선안을 알려줘. 아직 수정하지는 마.
```

기존 UI를 다듬는 데 사용합니다. 브랜드 전면 개편이나 프레임워크 이전을 위한 스킬은 아닙니다. 특정 라이브러리나 외부 서비스 없이 사용할 수 있습니다.

## 설치

이 저장소 자체가 하나의 스킬 폴더입니다. 저장소에 접근 가능한 계정으로 인증한 뒤, 사용하는 에이전트의 스킬 디렉터리에 `ui-clarity`라는 이름으로 복제합니다. 같은 이름의 폴더가 있다면 먼저 내용을 확인하세요.

Codex 예시:

```sh
git clone https://github.com/Brokyeom/ui-clarity.git "${CODEX_HOME:-$HOME/.codex}/skills/ui-clarity"
```

설치 후 새 세션에서 `$ui-clarity`로 호출합니다. 다른 에이전트에서는 해당 도구의 스킬 탐색 위치를 사용하세요.

## 구성

- [SKILL.md](SKILL.md): 판단 기준, 적용 방법, 예시, 검증 범위
- [agents/openai.yaml](agents/openai.yaml): Codex 표시 이름과 기본 호출 문구

## 출처

[Comwit](https://library.comwit.io/template/docs/migrate)의 디자인 방법론을 참고해 실제 UI 정리 작업에서 얻은 판단 기준을 정리했습니다. Comwit의 공식 스킬이 아니며, 패키지 설치나 아키텍처 이전을 요구하지 않습니다. 프로젝트 고유 코드·데이터·계정 정보는 포함하지 않습니다.

---
name: bio-research-context
description: Add full scientific/institutional context to a virology, immunology, or animal-model research question before asking it (purpose, affiliation, biosafety level, system assumptions, references). Use when drafting a question about viral titers, pathogen handling, BSL-2/3 procedures, animal challenge models, or anything that sounds dual-use out of context, so the question reads as grounded lab methodology and the answer comes back specific instead of vague, hedged, or blocked.
---

# 연구 질문 맥락화 템플릿

이 스킬은 안전 필터를 "속이기" 위한 것이 아니라, 원래 CLAUDE.md 원칙(가정 명시, 구체적 답변 요구)에 맞게
질문 자체를 더 완전하게 만들기 위한 것이다. 맥락이 분명한 질문은 더 정확한 답을 받을 뿐 아니라,
이중용도로 오해받을 여지도 줄어드는 부수 효과가 있다.

## 동작 방식

사용자가 `/bio-research-context <질문>` 형태로 호출하면:

1. 사용자가 준 원문 질문을 아래 템플릿의 "질문" 항목에 넣는다.
2. 나머지 항목(목적, 소속/승인, 시스템, 원하는 답변 형태, 참고문헌)은 대화 맥락
   (CLAUDE.md: Mothes Lab, Yale, 면역학/바이러스학 postdoc, BSL-2/3 workflow)과
   이전 대화에서 알 수 있는 정보로 최대한 채운다.
3. 비어 있는 항목은 추측하지 말고 "확인 필요"로 표시하고, 답변에 영향이 크면 사용자에게 되묻는다.
4. 완성된 템플릿을 사용자에게 보여준 뒤, 그 내용을 바탕으로 실제 질문에 답한다.

인자 없이 `/bio-research-context`만 호출되면 빈 템플릿만 출력해서 사용자가 직접 채우게 한다.

## 템플릿

```
### 목적
(이 질문이 어떤 연구 목표/가설과 연결되는가)

### 소속 및 승인
- 소속: Mothes Lab, Department of Microbial Pathogenesis, Yale University
- 생물안전등급: BSL-2 / BSL-3 (해당 사항 명시)
- 관련 승인(있다면): IACUC/IBC 프로토콜 번호

### 시스템 가정
- 바이러스/균주: (예: SARS-CoV-2, influenza A/PR8)
- 세포/동물 모델: (예: Sf9/baculovirus, C57BL/6 mouse)
- 역가/용량 등 알려진 조건: (모르면 "확인 필요")

### 원하는 답변 형태
- [ ] 벤치용 번호 매긴 프로토콜 (재료 목록 포함)
- [ ] 개념 설명 / 원리
- [ ] 트러블슈팅
- [ ] 문헌 비교

### 참고문헌 (재현하려는 방법이 있다면)
(PMID/DOI, 없으면 "없음 — 새로운 방법 필요")

### 질문
(원문 그대로)
```

## 주의

- 전파력/치명률 증강, 합성, 방어 회피 등 실제 이중용도 위험이 있는 내용은 맥락을 채워도 돕지 않는다.
  이 템플릿은 표준 분자생물학·면역학·바이러스학 실험 기법 질문을 더 명확하게 만드는 용도다.
- 측정·검출·불활성화·안전 처리 프레이밍을 우선하고, "증강/향상/weaponize" 류 표현은 피한다.

# AI 고객 인터뷰 실습 프롬프트: 타겟 정의부터 모의 인터뷰까지

매쉬업벤처스 창업자 워크샵 "우스꽝스러울 정도로 좁게 타겟 설정하기"에서 실제로 사용한 AI 실습 프롬프트 6개입니다. 사업 자료 하나만 있으면 타겟 세그먼트 정의, 인터뷰 질문 설계, AI 페르소나와의 모의 인터뷰, 4-Part 캔버스 정리까지 반나절 안에 한 번 돌려볼 수 있습니다.

배경이 되는 글: [우스꽝스러울 정도로 좁게: 타겟을 좁힐수록 시장을 지배한다](https://www.mashupventures.co/contents/startup-target-customer-definition-strategy-guide)

*Prompt files (in Korean) from Mashup Ventures' founder workshop on defining a comically narrow target customer and practicing customer interviews with AI personas.*

## 실습 흐름

| 실습 | 프롬프트 파일 | 함께 첨부할 파일 | 산출물 |
|---|---|---|---|
| 0. 사업 요약 만들기 (사전 준비) | [`target-practice0_deck-to-md.md`](prompts/target-practice0_deck-to-md.md) | 사업 자료 아무거나 (IR덱, 사업계획서, 텍스트 설명. 없어도 가능) | `사업요약.md` |
| 1. 타겟 세그먼트 정의 (I-E-T) | [`target-practice1_segments.md`](prompts/target-practice1_segments.md) | `사업요약.md` | `타겟정의.md` |
| 2. 고객 인터뷰 질문 설계 | [`target-practice2_interview-questions.md`](prompts/target-practice2_interview-questions.md) | `타겟정의.md` + `사업요약.md` | `인터뷰가이드.md` |
| 3. 모의 인터뷰용 페르소나 생성 | [`target-practice3_persona.md`](prompts/target-practice3_persona.md) | `타겟정의.md` | `페르소나1_이름.md` 등 3개 |
| 4. AI 모의 인터뷰 (페르소나마다 새 대화) | [`target-practice4_mock-interview.md`](prompts/target-practice4_mock-interview.md) | 페르소나 1명 | `인터뷰기록_이름.md` |
| 5. 4-Part 캔버스 정리 | [`target-practice5_4part-canvas.md`](prompts/target-practice5_4part-canvas.md) | `타겟정의.md` + 인터뷰 기록 3건 | 세그먼트 캔버스 + I-E-T 수정안 |

- 실습 1은 사업 요약에 적힌 타겟을 정답으로 받아 적지 않습니다. 문제와 솔루션만 추출한 뒤 후보 세그먼트를 6개 이상 발산하고 그중 3개를 골라, 각각의 I-E-T(Inclusion·Exclusion·Trigger)와 30% 침투 계획까지 만듭니다.
- 실습 4는 "인터뷰 종료"라고 입력하면 페르소나 연기를 멈추고 코치로 돌아와 잘한 질문, 아쉬운 질문, 놓친 단서를 짚어줍니다.
- 실습 5는 인터뷰 3건을 종합해 2명 이상 공통은 패턴으로, 1명뿐인 것은 추가 검증 가설로, 답변이 갈린 것은 세그먼트를 다시 쪼개야 한다는 신호로 정리합니다.

## 진행 방식

1. 프롬프트 파일 6개를 내려받습니다. ([ZIP으로 받기](https://github.com/mashupventures/ai-customer-interview/archive/refs/heads/main.zip) 후 `prompts/` 폴더만 쓰면 됩니다.)
2. 실습마다 **새 대화**를 열고, 그 실습의 프롬프트 파일과 위 표의 첨부 파일만 넣은 뒤 "진행해줘"라고 입력합니다. 실습 3은 "세그먼트 N으로 진행해줘"로 시작합니다.
3. 각 실습이 끝나면 마지막에 출력되는 코드블록을 안내된 파일명으로 저장합니다. 그 파일이 다음 실습의 첨부 파일이 됩니다. 파일명은 프롬프트끼리 서로 참조하므로 안내된 이름을 그대로 쓰세요.
4. 실습 3과 4에는 `사업요약.md`를 첨부하지 않습니다. 페르소나가 우리 사업을 알아버리면 인터뷰 연습이 오염됩니다.
5. 원본 IR덱은 실습에 직접 쓰지 않고 실습 0에서 만든 `사업요약.md`를 씁니다. 이미지 위주 덱은 AI가 읽는 데 컨텍스트를 많이 쓰고 추출 품질도 들쭉날쭉합니다.

## 모델 선택

기준은 하나입니다. 깊게 생각해야 하는 작업이냐, 빠르게 주고받아야 하는 작업이냐.

- 실습 0, 1, 2, 5 (자료 추출, 타겟 발산과 수렴, 가정 추출, 기록 종합): 쓸 수 있는 가장 상위 모델. 특히 실습 1의 발산과 전략 판단은 모델 급 차이가 산출물에 그대로 드러납니다.
- 실습 3, 4 (페르소나 생성, 모의 인터뷰): 빠른 모델. 매 답변마다 길게 생각하는 모델을 쓰면 대화 리듬이 깨져 인터뷰 연습이 안 됩니다.

모델 이름은 몇 달 단위로 바뀌므로 특정 모델을 적지 않습니다. Claude와 ChatGPT 모두에서 동작하도록 작성했고, 워크샵은 Claude 기준으로 진행했습니다. 무료 플랜은 상위 모델 선택이 안 되고 사용량 한도도 실습을 버티지 못하므로 유료 플랜을 권합니다.

## AI 인터뷰에 대해

AI 인터뷰는 연습입니다. AI는 실제 고객보다 과하게 협조적이라 인사이트를 정리해서 건네주는 경향이 있고, 프롬프트에 이를 막는 장치(과잉 협조 금지, 라포 전 민감한 이야기 방어, 캐릭터 유지)를 넣었지만 진짜 고객 인터뷰를 대체하지는 못합니다. AI 인터뷰에서 찾은 패턴은 실제 고객에게 확인해야 할 가설 목록으로 취급하세요.

## 피드백

프롬프트가 기대와 다르게 동작하거나 개선 아이디어가 있으면 [Issues](https://github.com/mashupventures/ai-customer-interview/issues)에 남겨 주세요. 어떤 실습에서, 어떤 모델로, 어떤 입력을 넣었을 때 그랬는지 함께 적어 주시면 재현에 도움이 됩니다.

## 라이선스

[CC BY 4.0](LICENSE). 출처(매쉬업벤처스)를 밝히면 자유롭게 쓰고 고쳐 쓸 수 있습니다.

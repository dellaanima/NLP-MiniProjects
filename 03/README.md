# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 박혜원
- 리뷰어 : [이태훈](https://github.com/git-ThLee)


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네

- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 주석이 많지는 않아서 약간 힘들었습니다..! 똑똑한 사람들의 코드는 이해하기 어렵웝요 ㅠ

- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 실행에 필요한 모든 코드를 함수화하여 작성하여, 코드가 에러가 발생해도 금방 해결할 것같습니다.

- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 제대로 이해하지 않았다면 저런 코드가 나올 수 없을 것 같습니다.

- [O] 코드가 간결한가요?
  > 네 필요한 부분에 적절한 코드를 사용하여 주석이 없음에도 읽고 이해할 수 있었습니다.

# 인상 깊었던 부분

- 사유 : 일반적으로 모델을 학습할 때, f1_score는 제공하지 않습니다. 필요한 정보를 직접 코드로 작성하여 f1_score를 표현했다는 것이 대단합니다!

```python
def f1_m(y_true, y_pred):
    precision = precision_m(y_true, y_pred)
    recall = recall_m(y_true, y_pred)
    return 2*((precision*recall)/(precision+recall+K.epsilon()))

```
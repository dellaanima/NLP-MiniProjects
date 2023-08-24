# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 박혜원
- 리뷰어 : 김연수


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [X] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
     
- [X] 주석을 보고 작성자의 코드가 이해되었나요?
  > 네, 마크다운과 주석이 자세히 적혀있어, 전반적인 코드를 이해하는 데에 도움이 되었습니다.
- [X] 코드가 에러를 유발할 가능성이 없나요?
  > 모두 에러 없이 동작하는 것으로 보입니다.
- [X] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네, 주어진 과제에 추가적으로 여러가지 실험을 해보신 것으로 보아, 기본 코드에 대한 이해를 바탕으로 작성하신 것 같습니다.
- [X] 코드가 간결한가요?
  > 네, 불필요한 부분 없이 간결합니다.

# 예시
1. 데이터 시각화를 통해 사용하고자 하는 데이터의 특성에 대한 이해도를 높일 수 있었습니다.
```python
#데이터 길이 시각화 함수
def show_sentence_length(sentence_num, title, range_=[0, 500]):
    plt.figure(figsize=(13, 5))
    plt.suptitle(title, fontsize=14)

    plt.subplot(1, 2, 1)
    plt.hist(sentence_num, bins=range_[1], range=range_, facecolor='b', label='train')
    plt.xlabel('Number of question')
    plt.ylabel('Count of question')

    plt.subplot(1, 2, 2)
    plt.boxplot(sentence_num, labels=['token counts'], showmeans=True)

    plt.show()
```
2. 다른 데이터를 가지고 추가적으로 실험해보신 결과물이 있어서, 데이터셋에 따른 성능차이도 확인할 수 있었습니다.

   
# 참고 링크 및 코드 개선

# AIFFEL Campus Online 5th Code Peer Review Templete
- 코더 : 박혜원
- 리뷰어 : 윤상현


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네

- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 주석이 많지는 않아서 약간 힘들었습니다..!

- 아래의 내용들이 굉장히 좋았습니다.
  문제에서 제시한 부분에서 추가적으로 FastText, W2V, Komoran, Mecab 등등
  koNLPy 내부에 있는 대부분의 방법으로 진행한 점이 너무나도 좋았습니다.
  ```python
  plt.figure(figsize=(12, 12))
  plt.style.use('ggplot')
  
  # Define subplots upfront
  ax1 = plt.subplot(2, 1, 1)
  ax2 = plt.subplot(2, 1, 2)
  
  # Define metrics and their corresponding subplots
  metrics_axes = [
      ('loss', 'val_loss', ax1),
      ('accuracy', 'val_accuracy', ax2)
  ]
  
  history_selection = [0, 1, 3, 8, 9]
  
  for i in history_selection:
      history = histories[i]["history"]
  
      color = next(ax1._get_lines.prop_cycler)['color']
  
      for metric, val_metric, ax in metrics_axes:
  #         ax.plot(history.history[metric], 
  #                 linestyle='--', marker='x', color=color, 
  #                 label=f"{metric} :: {histories[i]['name']}")
          ax.plot(history.history[val_metric], 
                  linestyle='-', marker='o', color=color, 
                  label=f"{val_metric} :: {histories[i]['name']}")
          ax.set_xlabel('Epoch')
          ax.legend(loc='upper left', bbox_to_anchor=(1, 1))
  
  plt.tight_layout()
  plt.show()
  ```

- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 없어 보입니다.

- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 제대로 이해하지 않았다면 저런 코드가 나올 수 없을 것 같습니다.

- [O] 코드가 간결한가요?
  > 네 필요한 부분에 적절한 코드를 사용하여 주석이 없음에도 읽고 이해할 수 있었습니다.

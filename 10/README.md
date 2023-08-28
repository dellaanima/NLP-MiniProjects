# AIFFEL Campus Online 5th Code Peer Review
- 코더: 박혜원
- 리뷰어: 김석영


# PRT(PeerReviewTemplate) 
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.

- [O] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
  > 네. 모든 코드가 정상적으로 동작하고, 루브릭의 평가문항과 상세기준들을 모두 충족하였습니다.
- [O] 주석을 보고 작성자의 코드가 이해되었나요?
  > 네. 방대한 양의 코드들을 Task별로 순차적으로 제목을 달아 잘 구분해놔서 코드를 이해하는 데 큰 도움이 되었습니다.
- [O] 코드가 에러를 유발할 가능성이 없나요?
  > 없습니다.
- [O] 코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 네. 노드에서 제시한 데이터셋과 형태소분석기 이외에 다른 dataset과 분석기를 이용하는 등 배운 내용의 단순한 적용과 이해 이상으로 능숙하게 코드를 작성하고 구현하였습니다.
- [O] 코드가 간결한가요?
  > 네. 불필요한 코드(주석 포함)가 없고, Task별로 간결하게 작성돼 있습니다.

# 예시
```python
def tokenize(corpus, vocab_size, maxlen, encoder_TF=True):
    # Tokenizer 객체 생성
    tokenizer = tf.keras.preprocessing.text.Tokenizer(
        filters='',            # 토큰화할 때 제거할 문자 지정 (여기서는 없음)
        oov_token="<UNK>",     # Out-Of-Vocabulary (단어 집합에 없는 단어를 나타내는 토큰)
        num_words=vocab_size   # 최대 단어 수 제한
    )

    corpus_input = corpus

    # encoder 데이터일 때, (즉 '한국어') Mecab 으로, 형태소 단위로 쪼개기
    if encoder_TF:
        m = MeCab()
        corpus_input = []
        for sentence in corpus:
            # 문장을 형태소로 분석하여 리스트로 변환하여 저장
            corpus_input.append(m.morphs(sentence))


    # Tokenizer를 훈련 데이터에 맞춰 학습 (위에 설명 참고)
    tokenizer.fit_on_texts(corpus_input)

    # vocab_size를 초과하는 빈도수의 단어들을 삭제
    if vocab_size is not None:
        words_frequency = [w for w, c in tokenizer.word_index.items() if c >= vocab_size + 1]
        for w in words_frequency:
            del tokenizer.word_index[w]
            del tokenizer.word_counts[w]

    # 문장을 정수 시퀀스로 변환하여 저장
    tensor = tokenizer.texts_to_sequences(corpus_input)

    # 정수 시퀀스를 maxlen에 맞게 Padding 처리
    tensor = tf.keras.preprocessing.sequence.pad_sequences(
        tensor,
        padding='post',
        maxlen=maxlen
    )

    # 토큰 수 통계 출력
    token_lengths = [len(tokens) for tokens in tensor]
    max_tokens = max(token_lengths)

    print(f"Maximum tokens: {max_tokens}")

    return tensor, tokenizer
```
```python
examples = [
    "아버지가 방에 들어가신다.",
    "저는 지금 공부를 하고 있어요.",
    "비가 올 수 있으니 꼭 우산을 챙기세요.",
    "컴퓨터가 고장났어요.",
    "저희 내일 저녁 7시에 만날래요?",
    "현재 날씨는 28도 입니다.",
    "당신을 정말 사랑해요.",
    "저는 음악을 들으면서 산책하는 것을 좋아해요.",
    "최근에 재밌게 본 영화가 있나요?",
    "여행 가고 싶어요."
]
```

# 참고 링크 및 코드 개선

```python

```

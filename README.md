# PTT word embedding
1. 2018/04/11 以PTT文本為輸入數據，進行Word Embedding模型訓練。一些單字可以看出關聯性。

# PTT title generator base on Encoder-Decoder-model

PTT title generator from content base on seq2seq model.
1. 2018/03/28. 完成初步multi-layer LSTM seq2seq model。
2. 2018/03/29. 加入2L regularization, dropout防止overfitting，並加入clip_by_norm避免無法收斂。
3. 2018/03/30. 加入attention, directional改善模型。
4. 2018/04/01. 訓練時TrainingHelper、GreedyEmbeddingHelper混合使用。一開始訓練時decoder需要輸入target幫助訓練，所以TrainingHelper機率大；後期model盡量與驗證時相同，所以GreedyEmbeddingHelper機率大。
5. 2018/04/22. 調整initializer，並將計算改為float64 (原先float32時在計算regularization L2時會NaN)。現在可以對文章自動生成標題，且有一定程度的關聯性。

# PTT push generator base on Encoder-Decoder-model
1. 2018/04/23. 訓練每篇文章的第一位推文。

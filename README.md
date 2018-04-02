# PTT-title-generator-Encoder-Decoder-model

PTT title generator from content base on seq2seq model.
1. 2018/03/28. 完成初步multi-layer LSTM seq2seq model。
2. 2018/03/29. 加入2L regularization, dropout防止overfitting，並加入clip_by_norm避免無法收斂。
3. 2018/03/30. 加入attention, directional改善模型。
4. 2018/04/01. 訓練時TrainingHelper、GreedyEmbeddingHelper混合使用。一開始訓練時decoder需要輸入target幫助訓練，所以TrainingHelper機率大；後期model盡量與驗證時相同，所以GreedyEmbeddingHelper機率大。

# 幾個待改善的重點問題
1. 生成標題常常最後無法中斷，無意義重複生出特定字詞。(2018/04/01已解決，但現在變成生成太短)
2. 看起來較相近的標題生成，不在loss最低的epoch中。
3. 標題生成與輸入文本關係度不高，同一個epoch有比較常出現的字詞。

# 改善方向
1. 研究一下decoder的兩個helper如何訓練、驗證，或自己設計helper。
2. 是否需要改進loss function和optimizer？
3. 或許是encoder output state訓練不佳？

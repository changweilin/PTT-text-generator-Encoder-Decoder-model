# PTT-title-generator-Encoder-Decoder-model

PTT title generator from content base on seq2seq model.
1. 2018/03/28. 完成初步multi-layer LSTM seq2seq model。
2. 2018/03/29. 加入2L regularization, dropout防止overfitting，並加入clip_by_norm避免無法收斂。
3. 2018/03/30. 加入attention, directional改善模型。

# 幾個待改善的重點問題
1. 生成標題常常最後無法中斷，無意義重複生出特定字詞。 (研究一下decoder在train和test兩種helper的差異，或自己設計help)
2. 看起來較相近的標題生成，不在loss最低的epoch中。 (研究一下loss function和optimizer如何改進)
3. 標題生成與輸入文本關係度不高，同一個epoch有比較常出現的字詞。 (是encoder output state訓練不佳？)

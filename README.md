# PTT-title-generator-Encoder-Decoder-model

PTT title generator from content base on seq2seq model.
.2018/03/28. 完成初步multi-layer LSTM seq2seq model.
.2018/03/29. 加入2L regularization, dropout防止overfitting，並加入clip_by_norm避免無法收斂.
.2018/03/30. 加入attention, directional改善模型.

# 幾個重點問題
1. 生成標題常常最後無法中斷，無意義重複生出特定字詞.
2. 看起來較相近的標題生成，不在loss最低的epoch中.
3. 標題生成與輸入文本關係度不高，同一個epoch有比較常出現的字詞.

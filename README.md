# seq2seq-attnetion-word
seq2seq attnetion word

利用seq2seq attention 字符級別訓練

使用方式：

    test = seq2seq_Attention_token_all ('P4_big_BN.h5', 'QA_all_token.txt') #參數說明第一個參數為儲存權重黨名稱，第二個參數為輸入txt檔

    test.train() #訓練模型

    model = test.create_model() #建立推理模型
    encoder_Inference, decoder_Inference = test.createAttentionInference(model)
    #建立推理模型

    while True:
        text = input('【input Answer】 \n' ) #輸入問句
        result = test.translate(text, encoder_Inference, decoder_Inference, True).replace(" ","") #產生問句
        print(result) #列印問句

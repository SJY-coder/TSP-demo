# TSP-demo
stock prediction model using sentence_transformers (RoBERTa) for sentiment analysis and neural network for stock prediction.
本プロジェクトの目標は当日の株式の情報と当日の人気ニュース（本プロジェクトでは使わなかったですが、目標としてTwitterのAPIを用いて人気tweetを使うことです。）をもとに一日後の株の変動価額を予想することです。

ここではKaggleからのDaily News for Stock Market Predictionのデータセットを使いました。

url-- https://www.kaggle.com/aaron7sun/stocknews

このプログラムを書いた当時には提出を想定せずにコメントを英語に書いた点、何とぞ理解いただきたく、ご承知ください。

ニュースなどでは自然後が使われているため、sentence_transformers（pretrained by RoBERTa）というパイソンライブラリーを用いて各文章を意味を持つベクトルとして表現しました。

一日には25個のニュースがありまして、ベクトル化した文章をRNNにインプットしｎ次の特性を出力できるようにしました。出力された特性はDNNに入れて出た株価の特性と合流され、また新しいDNNに入って次の日の株価を予想できることを目標としました。

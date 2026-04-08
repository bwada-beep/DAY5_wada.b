\# API 仕様・技術メモ

本アプリで使用している Gemini API に関する詳細情報です。

\#\# 1\. 使用モデル・エンドポイント  
\- \*\*使用モデル\*\*: Gemini 2.5 Flash  
  \- 音声、マルチモーダルな処理に特化した、高速かつ軽量な最新世代のモデルを採用。  
\- \*\*エンドポイント\*\*: \`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent\`  
\- \*\*リクエスト形式\*\*: POST (JSON)  
\- \*\*音声送信形式\*\*: \`inline\_data\` (Base64エンコード)

\#\# 2\. 参照リファレンス  
\- \*\*Gemini モデルガイド\*\*: \[https://ai.google.dev/gemini-api/docs/models?hl=ja\](https://ai.google.dev/gemini-api/docs/models?hl=ja)  
\- \*\*Audio ガイド\*\*: \[https://ai.google.dev/gemini-api/docs/audio\](https://ai.google.dev/gemini-api/docs/audio)

\#\# 3\. 利用制限 (無料プラン)  
\- \*\*RPM (1分あたりのリクエスト)\*\*: 15回  
\- \*\*RPD (1日あたりのリクエスト)\*\*: 1,500回  
\- \*\*特徴\*\*: 2026年現在、開発者向けの無料枠内で高速な音声解析が可能な最適なモデルとして選定。

\#\# 4\. プログラムの実装仕様  
\- \*\*音声処理\*\*: JavaScriptの \`FileReader\` APIを使用して、ユーザーが選択したバイナリファイルをBase64文字列に変換。  
\- \*\*ワークフロー\*\*:   
  1\. 音声データの文字起こしをリクエスト。  
  2\. 取得したテキストデータを再度Geminiに渡し、要約と要点抽出を依頼する2段階構成。  

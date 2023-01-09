#MVD 
# ELMo 
Contextual language embedding 
Embeddings from Language Models (2018, AllenAI) 
Používá bidirectional [[LSTM|LSTM]] pro tvorbu embeddingů. Embedding je vytvořen v závislosti na kontextu slova. Model je založen na znacích. Lze vytvořit embedding pro slovo, které není ve slovníku => Místo použití slovníku (např. [[Word2Vec|Word2Vec]]) vytváříme vektory za běhu.
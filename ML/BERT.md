#MVD
# BERT
Bidirectional Encoder Representations from Transformers.
Z [[Transformer|Transformeru]] využívá pouze kodéry (encoder). Neobsahuje Masked self attention. Predikce slova při trénování není založena pouze na předchozích, ale i na budoucích slovech. Lze vytvořit slovní embedding závislý na kontextu (podobně jako u [[ELMo|ELMo]] modelu). 

Pre-training -> Jazykový model se učí dvě úlohy: 
- Predikce maskovaného slova ve větě.
- Predikce další věty (binární klasifikace). Na vstupu jsou dvě věty a cílem je určit, zda druhá věta následuje za první.

## Predikce maskovaného slova ve větě
15 % slov je při trénování náhodně maskováno
Postup: 
- V 80 % případů je slovo nahrazeno MASK tokenem
- V 10 % případů je nahrazeno náhodným jiným tokenem
- V 10 % případů je ponecháno beze změny
Masek může být více v jedné větě
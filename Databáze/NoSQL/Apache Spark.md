# Apache Spark
Framework pro distribuované výpočty (další je např. [[MapReduce|MapReduce]])

## Hlavní vlastnosti:
- Batch a stream processing, machine learning
- In-memory (narozdíl od MapReduce to nerozhází po síti)
- Fault tolerant
- Lazy evaluation (trigger je akce – např. uložení výsledku na disk)
- Immutable data, funkcionální programování
- Paralelní zpracování

Master/slave architektura
- Driver program
- Cluster manager
- Worker nodes

SparkContext
- Instance Spark aplikace
- Převod aplikace na orientovaný graf (DAG) jednotlivých úloh
Job:: počítá výsledek akce, největší jednotlivá akce výpočtu
Stage
- Fyzická jednotka výpočtu
- Od shuffle do shuffle (např. join, reduce,  agregace)
Task
- Výpočet jedné stage nad jednou částí dat
- V jednom vlákně na jednom exekutoru
- Např. 800 tasků na 800 načtení souborů z HDFS

## RDD 
Resilient Distributed Dataset (RDD) je kolekce objektů rozdělených na části, které jsou immutable. Přežije ztrátu worker node – ztracená partition se dopočítá. In-memory – rychlá a náročná na paměť.

Další jsou např. DataSet a DataFrame

## DataFrame

## Transformace vs. akce
Transformace
- Narrow:: potřebují data jen z jedné partition (map, union, filter, …)
- Wide:: potřebují data z více partition – vyžadují shuffle (groupByKey, join, ...)

![[Spark transormace.png]]

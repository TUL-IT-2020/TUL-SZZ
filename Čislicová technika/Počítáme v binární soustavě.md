# Počítáme v binární soustavě

Příklad:

| binary | unsigned | signed | fixed point |
| ------ | -------- | ------ | ----------- |
| 1010   | 10       | -6     | 1,25        |
| 0101   | 5        | 5      | 0,625       |
| 1111   | 15       | -1     | 1,875       |

## Pro případ signed:
Pro výpočty v dvojkovém doplňku lze nahlížet na hodnotu nejvyššího bitu jako na "zápornou".

| bits |     |     |     | Sum |
| ---- | --- | --- | --- | --- |
| 1    | 0   | 1   | 0   |     |
| -8   |     | 2   |     | -6  |

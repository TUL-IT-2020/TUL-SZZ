# Symetrie objektů

Čtverec: 4-prvkový objekt

> [!note] Dihedrální grupy
## 2D symetrie čtverce
- rotace o 90°

1-2
 |  |
4-3

| úhel | permutace    | cyklický index |
| ---- | ------------ | -------------- |
| 90˚  | (1234)       | $x_4$          |
| 180˚ | (13)(24)     | $x_2^2$        |
| 270˚ | (1432)       | $x_4$          |
| id   | (1)(2)(3)(4) | $x_1^4$        |
Polynom cyklického indexu:
$$
P_{2D}(x_1,x_2,x_3,x_4) = \frac{1}{4}(x_1^4 + x_2^2 + 2x_4)
$$

## 3D symetrie čtverce
2D + 
- osa vodorovně 
- osa svisle
- diag1
- diag2

1-2
 |  |
4-3

| symetrie  | permutace  | cyklický index |
| --------- | ---------- | -------------- |
| svisle    | (12)(34)   | $x_2^2$        |
| vodorovně | (14)(23)   | $x_2^2$        |
| diag1     | (1)(24)(3) | $x_1^2x_2$     |
| diag2     | (13)(2)(4) | $x_1^2x_2$     |
Polynom cyklického indexu:
$$
P_{3D}(x_1,x_2,x_3,x_4) = \frac{1}{8}(x_1^4 + 2x_1^2x_2 + 3x_2^2 + 2x_4)
$$

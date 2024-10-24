# Symetrie objektů

Čtverec: 4-prvkový objekt

## 2D
- rotace o 90°

| úhel | permutace    | cyklický index |
| ---- | ------------ | -------------- |
| 90˚  | (1234)       | $x_4$          |
| 180˚ | (13)(24)     | $x_2^3$        |
| 270˚ | (1432)       | $x_4$          |
| id   | (1)(2)(3)(4) | $x_1^4$        |
$$
P_{2D}(x_1,x_2,x_3,x_4) = \frac{1}{4}(x_1^4 + x_2^2 + 2x_4)
$$

## 3D
2D + 
vodorovně 
svisle
diag1
diag2

| symetrie | permutace  | cyklický index |
| -------- | ---------- | -------------- |
|          | (12)(34)   | $x_2^2$        |
|          | (14)(23)   | $x_2^2$        |
|          | (1)(24)(3) | $x_1^2x_2$     |
|          | (13)(2)(4) | $x_1^2x_2$     |

$$
P_{3D}(x_1,x_2,x_3,x_4) = \frac{1}{8}(x_1^4 + 2x_1^2x_2 + 3x_2^2 + 2x_4)
$$

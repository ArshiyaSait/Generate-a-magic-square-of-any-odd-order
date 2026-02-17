# Generate-a-magic-square-of-any-odd-order
import numpy as np
order = int(input("Enter order of magic square (order must be odd): "))
if order % 2 == 0:
    order += 1
    print("Given order is even so it is incremented by 1.")
magic = np.zeros((order, order), dtype=int)
n = 1
i, j = 0, order // 2
while n <= order * order:
    magic[i][j] = n
    n += 1
    new_i, new_j = (i - 1) % order, (j + 1) % order
    if magic[new_i][new_j]:
        i = (i + 1) % order
    else:
        i, j = new_i, new_j
print("Generated Magic Square is:\n")
for row in magic:
    print("|", end="")
    for val in row:
        print("%4d |" % val, end="")
    print()
    print("-" * (order * 6))

OUTPUT:
Enter order of magic square (order must be odd): 5
Generated Magic Square is:

|  17 |  24 |   1 |   8 |  15 |
------------------------------
|  23 |   5 |   7 |  14 |  16 |
------------------------------
|   4 |   6 |  13 |  20 |  22 |
------------------------------
|  10 |  12 |  19 |  21 |   3 |
------------------------------
|  11 |  18 |  25 |   2 |   9 |
------------------------------

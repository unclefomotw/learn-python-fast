# 第六章：資料類型 - tuple (元組)

## tuple 跟 list 很類似，但是「不能變」

tuple 是另一種資料類型：把一些資料列出來，像這樣，用圓圓的小括號括起來。

```python
my_name = ("Mary", "Lin")
birthday = (1996, 2, 14)
weather = (20, 32, 25, 10)

print(my_name[0])  # Mary

for i in weather:
    print(i)
# 分別印出 20, 32, 25, 10 四行
```

看起來跟 list 很像？沒錯。但有一個很重要的差別：tuple 裡面的元素不能變動

```python
# list
my_name = ["Mary", "Lin"]
my_name[1] = "Chen"  # 這可以

my_name = ("Mary", "Lin")
my_name[1] = "Chen"  # 這不行，會錯誤！

my_name = ("Mary", "Chen")  # 這樣才可以，但是
                            # 原來的 ("Mary", "Lin") 就不見了
```

所以 list 的 `.append()` 加東西的, 在 tuple 上也不行

tuple 就像用原子筆寫在紙上的清單，寫上去以後就不能改了。你要「更改」就是拿另一張紙重新寫。

這樣看起來 list 比較靈活，為什麼要用 tuple？除了一些細膩的地方（例如 hash, 速度），個人覺得在「語感」上也有一點點差別是，tuple 偏向用來「表示」、「描述」某個東西的本質或不變的特性。我們會稱 tuple 是 "immutable", 無法突變的（相較於 list 是 mutable）

## unpack

Unpack 不僅限於 tuple, list 也可以（能夠一個個數的都可以）

```python
x, y, z = (2, 3, 5)
print(y)  # 3

fruits = ["蘋果", "香蕉", "水梨"]
apple, banana, pear = fruits
print(pear)  # 水梨

# 相當於
# apple = fruits[0]
# banana = fruits[1]
# pear = fruits[2]
```

也就是把等號右邊的一串東西（無論是 tuple 或 list）存到左邊的很多變數，不用寫很多行指令 -- 這種操作叫 unpack，把行李從箱子裡拿出來

不過等號左右兩邊的數量要一樣，否則程式會錯！

```python
x, y, z = (2, 3, 5, 7)  # 會有錯誤 ValueError
                        # too many values to unpack

apple, banana, pear = ["蘋果", "香蕉"]  # 會有錯誤 ValueError
                                       # not enough values to unpack
 ```
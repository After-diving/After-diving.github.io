# python 入门

## method

```python
#List
x1=[1,2,3,4,5,6,7,8,9]
#tuple
x2=(1,2,3,4,5,6,7,8,9)
#string
x3="123456789"
```

1. 求长度`len()`: len(x1), len(x2), len(x3)

2. 求最小`min()`:min(x1), min(x2), min(x3)

3. 求最大`max()`:max(x1), max(x2), max(x3)

4. 求和`sum()`:sum(x1), sum(x2)

---

5. 增加元素`append()`,追加在数组后面 : x1.append("3")

6. 增加多个元素`extend()`,追加在数组后面 : x1.extend([22,48])

7. 插入元素`insert(position,element)`  : x1.insert(2,55)

---

8. 删除元素`pop(index(optional))`,index可选,默认是最后一个,并且把这个元素返回回来 : x1.pop(2)
9. 删除元素`remove(element)`,根据元素内容删除数组查找的第一个元素,并且没有返回值 : x1.remove(7)
10. 关键字`del`: del x1[index]

---

11. 查找元素`index(element)`, 查找元素在列表中的索引位置,返回位置 : x1.index(7)

---

12. 反转队列`reverse()`, 反转对象是修改原来的队列,没有返回值 : x1.reverse()
13. 反转队列`x1[::-1]`, 有返回值 : x1[::-1]

---

14. 统计某个元素在列表中出现的次数`count(element)`,: x1.count(20)


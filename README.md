#ЗАДАНИЕ 17 ЛЕГКОЕ
fail = open('17_IZI.txt')
spis = [int(x) for x in fail]
v = []
a = []
for i in range(len(spis) - 1):
    if (spis[i] + spis[i + 1]) % 2 == 0:
        a.append(spis[i] + spis[i + 1])
for y in range(len(spis) - 2):
    if (spis[y] + spis[y + 1] + spis[y + 2]) % 2 != 0:
        v.append(spis[y] + spis[y + 1] + spis[y + 2])
if len(a) > len(v):
    print("0", max(a))
else:
    print("1", max(v))


#ЗАДАНИЕ 17 СРЕДНЕЕ
fail = open('17.txt')
spis = [int(x) for x in fail]
otv2 = 1
res = []
fib = [0, 1]
for y in range(2, 50):
    fib.append(fib[y - 2] + fib[y - 1])
minfib = min([x for x in spis if x in fib and len(str(x)) == 2])
for i in range(len(spis) - 1):
    if (spis[i] + spis[i + 1]) % minfib == 0:
        res.append(spis[i] + spis[i + 1])
        otv2 -= 1
    else:
        otv2 += 1
print(sum(res), otv2)


#ЗАДАНИЕ 17 СЛОЖНОЕ
fail = open('input.txt')
spis = [int(x) for x in fail]
res = []
for i in range(len(spis) - 3):
    spisi = [spis[i], spis[i + 1], spis[i + 2], spis[i + 3]]
    spisi.sort()
    spisi7 = [x for x in spisi if str(x).count('7') == 1]
    if (spisi[0] + spisi[3]) == (spisi[1] + spisi[2]):
        if len(spisi7) == 2:
            res.append(sum(spisi))
print(sum(res), len(res))

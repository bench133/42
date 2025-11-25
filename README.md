# 42
code15
f = open('26.txt')
l = f.readline()
limit = int(l.split()[0])
n = int(l.split()[1])
a = [int(x) for x in f.readlines()]
a.sort()
ns = 0
k = 0
for i in a:
    if ns + i <= limit:
        ns += i
        k += 1
        temp = i
    else:
        ns -= temp
        for j in a:
            if ns + j <= limit:
                temp = j
            else:
                break
        break
print(k, temp)

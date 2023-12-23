import random





c = 1
flag = False
O = []
a = int(input('Ширина - '))
b = int(input('Длина - '))
steps = random.randint(0,10)
map_ = []
for i in range(a):
    i = i + 1
    for j in range(b):
        j = j + 1
        map_.append([i,j])
print(map_)
pos_1 = int(input('Напишите положение робота по высоте  - '))
pos_2 = int(input('Напишите положение робота по ширине  - '))
pos = [[pos_1,pos_2]]
print(pos)
print(map_)
for i in map_:
    O.append('o')
for i in range(steps):
    print(f'Так выглядит карта - {O} ')
    vector = random.randint(1,4)
    if vector == 1:
        pos[0][0] =  pos[0][0] + 1
    elif vector == 2:
        pos[0][1] =  pos[0][1] + 1
    elif vector == 3:
        pos[0][0] =  pos[0][0] -1
    elif vector == 4:
        pos[0][1] =  pos[0][1] - 1
    print(pos)
    for i in map_:
        if pos[0] == i:
            O[map_.index(pos[0])] = 'x'
    if pos[0][0] == 0:
        print('робот на краю')
    if pos[0][0] == a:
        print('робот на краю')
    if pos[0][1] == 0:
        print('робот на краю')
    if pos[0][1] == b:
        print('робот на краю')
    if pos[0] not in map_:
        print('Вышел за карту')
        break
    flag = True
    ans = input('Продолжить? ')
if flag == True:
    print('Миссия заверешна')

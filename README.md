# :mortar_board: As a Student :mortar_board:
# :scroll:My name: Shmidt Gleb Artemovich
I'm a student of the Ural Federal University. Studying at IRIT-RTF at Programming Engineering programm.

## :bookmark: More about me :yum:
I've participated at Hackathon and have entered to the Top-Trek programm. Very clever :star:

## :boom: My hobbies and points of interests 
- Programming (obviously :grin:)
- Enjoing my life (unexpected :open_mouth:)
- Lifting weights (too strong :muscle::sunglasses::thumbsup:)
- Feeling nature (a.k.a Druid :herb::green_heart:)

## :dart: My skills
1. :computer: Back-end Programming
  - Python Scripts
  - Data Bases
  - APIs, Server Maintaining
2. :hammer: System Administration
  - Linux Bash Scripts
  - Resources Administration
3. :tv: Windowed App Development
  - Widgets Creating
  - App Design

## :calendar: My Schedule
| Day | Time | Place |
|-----------|------|-------|
| Monday    | 8:30-13:30 | University |
| Tuesday   | 12:00-19:10 | University, Gym |
| Wednesday | 8:30-19:10 | University |
| Thursday  | 12:00-17:30 | University, Gym |  
| Friday    | 8:30-19:10 | University |
| Saturday  | 10:15-13:30 | University |
| Sunday    | 10:00-14:00 | Gym |

## :pushpin: One of my first projects
:moneybag: This is a shop on Python
```python
#Магазин
import os
import pickle
if not(os.path.isfile('dict_of_products.pkl')):
    products_dict = {}
    with open('dict_of_products.pkl','wb') as f:
        pickle.dump(products_dict, f)

with open('dict_of_products.pkl','rb') as f:
    products_dict = pickle.load(f)

def Informer():
    print()
    for i in products_dict.keys():
        print(str(i).rjust(4,' ') + '. ' + products_dict[i][0].ljust(15,'.') + str(products_dict[i][1]).rjust(7,'.') + ' x ' + str(products_dict[i][2]))
    print()


while True:

    os.system('cls')

    print('Магазин')
    print()
    print('1. Модуль Администратора')
    print('2. Модуль Кассира')
    print('3. Модуль Информер')
    print('4. Модуль Закупки товара')

    modul = input('Выберите режим работы >> ')

    if modul == '1':
        while True:
            os.system('cls')
            print('Модуль АДМИНИСТРАТОР')
            Informer()
            select1 = input('Добавить новый товар в БД, да/нет - (1/0)? >> ')
            if select1 != '1': break
            Article_number = int(input('Введите код или артикул товара >> '))
            name = input('Введите наименование товара >> ')
            price = float(input('Введите цену за единицу товара >> '))
            quantity = int(input('Введите количество товара, находящегося на складе >> '))
            products_dict[Article_number] = [name, price, quantity]

    if modul == '2':
        os.system('cls')
        print('2. Модуль КАССИР')
        Informer()
        print('Формирование нового чека')
        summa = 0
        while True:
            select2 = int(input('(N) Артикул товара / (0) Завершение >> '))
            if select2 != 0:
                text = str(select2).rjust(4,' ') + '. ' + products_dict[select2][0].ljust(15,'.') + str(products_dict[select2][1]) + ' x '
                count1 = float(input(text))
                if count1 <= products_dict[select2][2]:
                    print('.'*40 + str(products_dict[select2][1]*count1).rjust(8,' '))
                    summa += products_dict[select2][1]*count1
                    products_dict[select2][2] = products_dict[select2][2] - count1
                else:
                    print('.'*17 + 'ОШИБКА' + '.'*17)
                    print('Этого количества товара на складе нет!!!')
            if select2 == 0:
                print('='*50)
                print('Итого:')
                print('.'*40 + str(summa).rjust(8,' '))
                print('Формирование чека завершено...')

                # 4.3
                print('Приложите карту...')
                balance_card = float(input('Введите остаток денежных средств на банковской карте >> '))
                if balance_card < summa:
                    print('Недостаточно средств на банковской карте, пополните баланс!')
                else: print('Оплата прошла успешно! Удачных покупок!')

                input('Pause...')
                break
                

    if modul == '3':
        os.system('cls')
        print('3. Модуль ИНФОРМЕР')
        Informer()
        


    if modul == '4':
        os.system('cls')
        print('4. Модуль ЗАКУПКИ ТОВАРА')
        print()
        print('На вашем складе...')
        Informer()
        print()
        select3 = int(input('Желаете закупить товар? (1) Да / (0) Нет >> '))
        os.system('cls')
        if select3 != 0:
            while True:
                Informer()
                print()
                select4 = int(input('(N) Артикул закупаемого товара / (0) Завершение >> '))
                if select4 != 0:
                    text = str(select4).rjust(4,' ') + '. ' + products_dict[select4][0].ljust(15,'.') + str(products_dict[select4][1]) + ' x '
                    supply = int(input(text))
                    products_dict[select4][2] = products_dict[select4][2] + supply
                    os.system('cls')
                if select4 == 0:
                    print('Закупка завершена!')
                    break
        
    with open('dict_of_products.pkl','wb') as f:
        pickle.dump(products_dict, f)
    
    print()
    print("Для завершения нажмите любую клавишу...")
    print("Press any key...")

    
    key=input()
```

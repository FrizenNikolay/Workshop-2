# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил:
- Фризен Николай Васильевич
- РИ-231113
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Научиться передавать в Unity данные из Google Sheets с помощью Python.

## Задание 1
### Выберите одну из игровых переменных в игре СПАСТИ РТФ: Выживание (HP, SP, игровая валюта, здоровье и т.д.), опишите её роль в игре, условия изменения / появления и диапазон допустимых значений. Постройте схему экономической модели в игре и укажите место выбранного ресурса в ней.
Ход работы:
Мной было выбрано здоровье управляемого игроком персонажа. Здоровье - переменная, чьё значение определяет продолжается ли игра или заканчивается. Здоровье понижается на определённое количество единиц при атаке противников и восполняется при активации улучшений "Восстановление здоровья", "+ Здоровье", "Вампиризм". Первое улучшение восполняет одну единицу здоровья каждые 3 секунды, второе - увеличивает максимальное допустимое значение здоровья на 10 и полностью восполняет его, третье - восстанавливает здоровье на величину равную 1% урона, нанесённого врагам. Диапазон допустимых значений от 0 (при этом значении игра заканчивается) до 30 (по умолчанию, но верхнюю границу можно изменить с помощью улучшения "+ Здоровье").
![image](https://github.com/user-attachments/assets/6f30fdb2-5f74-48ab-88c9-2210f75476d2)
В данной моделе продемонстрирован процесс изменения здоровья в рассматриваемой игре. В данном случае, краном выступают очки опыта, получаемые при убийстве врагов. Эти очки попадают в условный инвентарь, где их можно конвертировать в улучшение, которое восстановит здоровье (преобразователь). При этом игрок теряет очки улучшения (труба) и может потерять полученное в результате преобразований здоровье от атак противников (вторая труба).

## Задание 2
### С помощью скрипта на языке Python заполните google-таблицу данными, описывающими выбранную игровую переменную в игре “СПАСТИ РТФ:Выживание”. Средствами google-sheets визуализируйте данные в google-таблице (постройте график / диаграмму и пр.) для наглядного представления выбранной игровой величины. Опишите характер изменения этой величины, опишите недостатки в реализации этой величины (например, в игре может произойти условие наступления эксплойта) и предложите до 3-х вариантов модификации условий работы с переменной, чтобы сделать игровой опыт лучше.

С помощью скрипта, я построил зависимость между максимальным здоровьем и количеством взятия улучшения "+ Здоровье", а также зависимость количества восстановленного способностью "Вампиризм" здоровья от времени.
![image](https://github.com/user-attachments/assets/4196daf4-e9ce-45f2-8a7a-723552835ddf)

![image](https://github.com/user-attachments/assets/726499b9-7d83-47cc-bfcc-d6d50f7cc1b9)

Первая зависимость линейная, вторая резко меняет своё значение.
Одним из недостатков здоровья в рассматриваемой игре является отстутствие возможности его восстановления без улучшений. Для этого можно ввести расходуемые предметы, которые будут выполнять эту функцию. Так же, если обратить внимание на две рассмотренные зависимости, становится заметно, что при увеличении максимального числа здоровья, смысл в его пассивном восстановлении начинает со временем теряться, чтобы это исправить, можно сделать восстановление здоровья от способности "Вампиризм" не в единицах, а в процентах от максимального количества. Так же, можно сделать увеличение максимального уровня здоровья меннее эффективным с каждым новым уровнем улучшения "+ здоровье", чтобы добавить динамичности в прокачку.


## Выводы

В этой работе были изучены способы загрузки данных в гугл таблицу, с помощью скриптов на языке Python и переноса этих данных в Unity для последующей работы с ними непосредственно в проекте.

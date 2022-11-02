# Тотализатор

В первые 10 дней каждого гоночного интервала активируется возможность сделать два вида ставок  —  ставки на место команды в рейтинге и ставки на состязание между двумя командами. Ставки разыгрываются при окончании текущего гоночного интервала.

## Ставки на место в рейтинге

В этом разделе можно сделать ставку на то, попадёт ли команда в диапазон мест в рейтинге. Для этого необходимо выбрать команду, а также указать с какого по какое место в рейтинге, по-вашему, займёт команда, диапазон мест может быть любым, например, с 1 по 3 или

с 7 по 10 или даже с 5 по 5. Затем вы выбираете результат, на который ставите — попадут команды в выбранный интервал или нет.

1. Места указываются включительно.
2. Номер места не может быть больше чем число команд, участвующих в гонке.

## Ставки на состязание между двумя командами

В этом разделе выбираются две команда и делается ставка на одну из них.

Ставка будет считаться сыгравшей, если команда, на которую сделана ставка, будет выше второй команды в рейтинге текущего интервала. Общие правила.

1. Все ставки и ответы на них совершают пользователи платформы, то есть это децентрализованные ставки по принципу p2p. Пользователи играют друг с другом.
2. Минимальный размер ставки 10 CWD.
3. Комиссия платформы с каждой ставки составляет 10%.
4. Для определения победителя используется только рейтинг текущего гоночного интервала.
5. Ставки, на которые не ответили, признаются не сыгравшими. Ставка отменяется, и сумма ставки возвращается тем, кто её поставил. Комиссия системы не возвращается.
6. Первый ответ на ставку не может быть меньше уже поставленной ставки. То есть если ставка на событие 100 CWD, то первый ответ на эту ставку не может быть меньше 100 CWD. После первого ответа ставки могут быть в любыми.
7. При завершении гоночного интервала в каждой ставке определяются победители, и призовой фонд делится между победителями в той пропорции, в которой были внесены сыгравшие ставки.
8. Одинаковые ставки объединяются.
9. Ставки от одного игрока суммируются.

## Пример

Пусть игроки сделали ставки на победу между двумя командами следующим образом:

|  Игрок  | Команда 1 | Команда 2 |
| :-----: | :-------: | :-------: |
| Игрок 1 |    100    |           |
| Игрок 2 |    100    |           |
| Игрок 3 |           |    200    |
| Игрок 4 |           |    100    |

Мы видим, что Игрок 1 и Игрок 2 поставили ставку на команду 1, по правилам тотализатора первая ответная ставка не может быть меньше чем текущая ставка, поэтому Игрок 3, который захотел сделать ставку на команду 2 и при этом ставок на команду 2 ещё не было, поставил 200 CWD, то есть сумму ставок Игрока 1 и Игрока 2. Он мог бы поставить сумму большую, чем 200 CWD, но не меньше. После того как первый ответ на ставку был получен, можно делать ставки любой суммы больше 10 CWD на любую команду, таким образом будет формироваться игровой коэффициент. В нашем примере коэффициент составит 1:1,5.

Теперь допустим, что наступило завершение текущего игрового интервала, розыгрыш состоялся, и победила Команда 1. В этом случае распределение призов произойдет следующим образом:

* Всего ставок на сумму 500 CWD.
* Всего ставок победителей 200 CWD.
* Приз каждого победителя будет вычислен по формуле: (Всего\_ставок)/Всего\_ставок\_победителей × ставка\_игрока\_победителя. То есть Игрок 1, который поставил 100 CWD получит приз — 500/200 × 100 = 250 CWD, таким образом он заработал на данной ставке 150 CWD. Поскольку ставка Игрока 2 тоже была 100 CWD, то он также выиграл 250 CWD. Игроки 3 и 4 проиграли.

В случае ставки на место в рейтинге принцип расчета призов точно такой же.
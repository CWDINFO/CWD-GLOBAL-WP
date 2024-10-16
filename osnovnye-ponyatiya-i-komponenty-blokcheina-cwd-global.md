# Основные понятия и компоненты блокчейна CWD GLOBAL

## Транзакции

Когда пользователи хотят воспользоваться каким-либо блокчейном, они производят так называемые транзакции и передают их в сеть. В транзакциях содержится информация о том, какие конкретно действия пользователь хочет совершить. Распространенная операция — это простая операция перевода средств, которая сопровождается передачей особых инструкций, содержащих необходимую информацию для этого действия, такую как отправитель, получатель, сумма для перевода, а также дополнительное зашифрованное сообщение (memo).

## Блокчейн — распределенный реестр данных

Блокчейн выполняет функцию журнала (реестра) подписанных пользователем инструкций, которые становятся обязательным соглашением, как только они включаются в блок. После включения в блок, соглашения хранятся в течение неопределенного срока с помощью хеш-связанного списка (цепочки блоков). Из этой упорядоченной последовательности можно определить текущее состояние транзакций (иными словами: остатки на счетах) путем последовательной обработки всех транзакций, начиная с самого первого блока. Как мы увидим позже, программное обеспечение гарантирует, что инструкции, хранящиеся в цепочке блоков, успешно идентифицированы и проверены. Для проверки и обработки операций общий набор правил определяет последствия определенных действий, которые являются частью протокола цепочки блоков.

## Сеть

Блокчейн просто определяет средства хранения и может использоваться нераспределенным образом с одним участником, а также в распределенной ячеистой сети на базе Интернета, часто называемой одноранговой (P2P) сетью. В последнем случае несколько сторон связаны друг с другом таким образом, что входящие транзакции пересылаются каждому другому подключенному участнику. В конечном итоге транзакция достигает так называемого производителя блоков. Производитель блоков проверяет входящие транзакции по жестко запрограммированному протоколу и объединяет их в единый блок, который добавляется к существующей цепочке блоков. На этом этапе транзакция считается подтвержденной и выполненной. Влияние выполненной операции на текущее состояние транзакции определяется протоколом блокчейна.

Ядро блокчейна написано на языке программирования C++ с использованием библиотек Boost. Сервер на котором выполняется ядро блокчейна называется по-разному, чаще всего Witness, но также нода, узел блокчейна, заверитель, node.

Все узлы образуют полносвязную одноранговую сеть. По своей архитектуре ядро блокчейна это noSQL база данных и интерфейс коммуникации. То есть ядро получает от клиента транзакцию в виде JSON объекта, проверяет её, и если она корректная — отправляет её на те узлы, с которыми установлена связь, те узлы которые получили эту транзакцию также.

## Консенсус

Консенсус — это процесс, посредством которого сообщество приходит к общепризнанному недвусмысленному соглашению по части информации. В контексте блокчейнов консенсус означает согласие относительно правил действительности транзакций и порядка, в котором они соблюдаются блокчейном. В конечном итоге это приводит к соглашению о текущем состоянии, которое непреложно строится на основе этих правил действительности и последовательности транзакций. Наиболее известная схема консенсуса —это Proof-of-Work (PoW). Самым доминирующим ее недостатком является высокое энергопотребление и масштабируемость с точки зрения количества транзакций в секунду и времени подтверждения. Блокчейн CWD GLOBAL использует алгоритм под названием Delegated Proof of Stake (DPoS), который был разработан специально для замены расточительного процесса майнинга, увеличения пропускной способности и сокращения времени реакции блокчейна. DPoS позволяет генерировать новый блок с фиксированной скоростью (время производства и подтверждения блока) с минимальными вычислительными требованиями. Это означает, что блокчейн может обрабатывать больше транзакций за значительно меньшее время и почти без затрат по сравнению с блокчейнами на основе PoW. Производство блоков осуществляется набором так называемых витнесов (производителей блоков), которые сменяют друг друга. После каждого цикла порядок производителей блоков определенным образом рандомизируется, так что все стороны соглашаются с новым порядком.

## Протокол

Самая важная часть технологий блокчейн здесь именуется протоколом блокчейн. Он определяет поведение всей системы, включая последствия и побочные эффекты при обработке транзакций. Пользователи используют определенные функции, создавая транзакцию, содержащую конкретное требование (также называемое операцией). Поскольку блокчейн, как хранилище хранит только дополнительные изменения (например, переводы), окончательный баланс каждой учетной записи вместе с другой информацией необходимо отслеживать отдельно в текущем состоянии. Важно отметить, что протокол является определенным в том смысле, что одно и то же состояние генерируется при применении той же последовательности операций (как предусмотрено цепочкой блоков).

Это делает технологии блокчейн защищенными от несанкционированного доступа и поддающимися проверке.

В разработанном блокчейне CWD GLOBAL доступно более 90 операций (на начало 2022 года).

Каждая из них подключается к протоколу Blockchain как минимум три раза:

1. Проверка. Во время проверки необработанные инструкции (также называемые полезной нагрузкой) проверяются на непротиворечивость. Например, в случае перевода мы гарантируем, что сумма перевода будет положительной.
2. Оценка. На этапе оценки конкретная операция — инструкция проверяется на соответствие текущему состоянию цепочки блоков. В случае перевода мы гарантируем, что переводимая сумма доступна на счету отправителя.
3. Примечание. Hа этом этапе предпринимаются действия, изменяющие текущее состояние. В случае перевода мы уменьшаем баланс счета отправителя и увеличиваем баланс счета получателя в соответствии с количеством переданных токенов.

## Расширяемость

Программное обеспечение, лежащее в основе блокчейна CWD GLOBAL, имеет модульную структуру и выполняет свои операции независимо друг от друга. Это позволяет добавлять новые функции, когда соответствующий код, который реализует методы проверки, оценки и применения, становится полностью законченным. В некотором смысле операции с блокчейном CWD GLOBAL представляют собой смарт-контракты и позволяют расширить набор функций системы. Однако в отличие от других платформ смарт-контрактов, CWD GLOBAL Blockchain требует, чтобы новые функции были проверены основными разработчиками и одобрены держателями CWD, прежде чем они могут быть установлены посредством обновления протокола в масштабе всей сети. Как следствие, платформа считается гораздо более надежной, поскольку новые функции требуют прохождения нескольких этапов контроля качества. Эти обновления протокола хорошо скоординированы и уже происходили 3 раза (на 4 квартал 2021 г.).

## Производительность и масштабируемость

Блокчейн BitShares публично продемонстрировал поддержку более 3000 (трех тысяч) транзакций в секунду и более 22000 операций в секунду в распределенной тестовой сети. Эта технология может легко масштабироваться до 100 000 (ста тысяч) и более транзакций в секундус относительно простым улучшением производительности сервера и протоколов связи.

## Персонификация аккаунтов

Одной из интересных особенностей блокчейнов на базе Graphene/Bitshares являются именованные аккаунты, то есть в отличии от биткойна или этериума у вас есть не просто адрес кошелька, но и понятное название аккаунта, которое вы можете использовать при проведении транзакций. CWD GLOBAL использует удобочитаемые имена учетных записей, которые должны быть зарегистрированы вместе с открытыми ключами в цепочке блоков перед их использованием. Таким образом, блокчейн действует как преобразователь имени и открытого ключа, аналогичный традиционной службе доменных имен (DNS). Эти именованные учетные записи позволяют пользователям легко запоминать и передавать информацию о своих учетных записях вместо использования подверженных ошибкам адресов. В зависимости от индивидуальных потребностей приложения, использующие блокчейн CWD GLOBAL, могут создавать дополнительное условие, которое имеет полную поддержку системы KYC (знай своего клиента) с помощью так называемого белого списка, который обеспечивает максимальный контроль и прозрачность, когда это необходимо. В отличии от базового функционала Bitshares на платформе CWD GLOBAL разработан механизм защиты аккаунтов с помощью проверочного слова, который создается пользователем.

## Адресная книга

Для борьбы со скам-аккаунтами и различными фишинговыми схемами, а также для повышения удобства пользования платформой, был разработан полностью новый компонент — Адресная книга. В адресную книгу можно добавлять те аккаунты, с которыми пользователь часто взаимодействует, можно добавлять понятные описания к этим аккаунтам, и проводить транзакции с ними буквально одной кнопкой, не вводя каждый раз название аккаунта. Функционал адресной книги довольно большой, начиная от переводов до поиска объявлений в CWDex от определенного аккаунта. Добавить аккаунт в адресную книгу можно или через строку поиска, или из интерфейса обзора аккаунта (новая кнопка будет рядом с кнопкой «отправить сообщение»).

Об адресной книге важно знать, что она хранится в браузере (local storage), поэтому если вы добавили кого-то в контакты на телефоне, то на компьютере этот контакт не появится. Для того чтобы перенести контакты с одного устройства на другое можно воспользоваться кнопками Импорт и Экспорт, которые в свою очередь загружают адресную книгу в IPFS. В IPFS адресная книга хранится 24 часа и при этом она никак не привязана ни к какому аккаунту. Можно создавать белые списки, то есть адреса аккаунтов блокчейна, которые прошли проверку и вы уверены, что это ваш надежный партнер или черные списки адресов аккаунтов тех людей, которые себя в чем-то дискредитировали.

## Виды разрешений (авторизаций)

#### Active key (Ключ прав доступа)

Данный ключ используется для подписания транзакций, которые не изменяют параметры аккаунта.

#### Owner key (Ключ владельца)

Данный ключ используется для внесения изменений в аккаунт. В случае взлома аккаунта, этот ключ необходим для изменения ключей, привязанных к учетной записи.

#### Memo key (Ключ примечания)

Данный ключ используется для шифрования дополнительной информации, передаваемой вместе с транзакцией. При использовании шифрования, этот текст будет доступен для чтения только отправителю и получателю транзакции.

Блокчейн CWD GLOBAL создает разрешения для учетных записей, а не для криптографии, что упрощает использование.

Каждая учетная запись разделена на следующие типы разрешений:

* Разрешение владельца - это разрешение имеет административные полномочия для всей учетной записи и должно рассматриваться для стратегий «резервного копирования».
* Активное разрешение - позволяет получить доступ к средствам и некоторым настройкам учетной записи, но не может изменить разрешение владельца и, таким образом, считается «онлайн» разрешениями.

Полномочия состоят из одного или нескольких объектов, которые разрешают действие, такое как передача или обмен. Полномочия состоят из одной или нескольких пар имени учетной записи с весом. Чтобы получить действительную транзакцию, сумма весов от подписания сторон должна превышать порог, определенный в разрешениях. Каждая учетная запись может контролироваться любой взвешенной комбинацией других учетных записей и закрытых ключей. Это создает иерархическую структуру, которая отражает то, как права организованы в реальной жизни, и делает многопользовательский контроль над средствами проще, чем когда-либо. Многопользовательский контроль является самым большим фактором безопасности, и при правильном использовании он может практически исключить риск кражи из-за взлома.

## Иерархия сети

Блокчейн CWD GLOBAL использует первую своем роде иерархическую систему закрытых ключей для облегчения использования обычных и резервных ключей. Обычные (активные) ключи предназначены для повседневного использования, в то время как отдельный резервный ключ (ключ владельца) может использоваться для восстановления доступа к учетной записи в случае потери обычных ключей. В идеале ключ владельца должен храниться в автономном режиме и использоваться только тогда, когда необходимо изменить ключи учетной записи или восстановить утерянный ключ. Большая часть программного обеспечения, поддерживающего блокчейн CWD GLOBAL, также облегчает использование мастер-пароля, который локально шифрует ключи клиента.

## Зашифрованные сообщения в блокчейне CWD GLOBAL

Учетная запись в блокчейне CWD GLOBAL имеет связанный с ней так называемый открытый ключ записи, который позволяет инициировать зашифрованную связь между двумя сторонами с помощью общего секрета, полученного с помощью алгоритма Диффи-Хеллмана на эллиптической кривой. Это позволяет прикреплять зашифрованные сообщения к передачам токенов, которые могут расшифровать только отправитель и получатель.

Отправка зашифрованных сообщений на блокчейне CWD GLOBAL — платная и стоимость зависит от длины сообщения.

## Реферальная программа

Блокчейн CWD GLOBAL имеет интегрированную восьми уровневую реферальную систему, в отличии от одноуровневой системы BitShares. Более подробно условия участия в реферальной программе рассмотрены в соответсвующем разделе.

## Комиссионные сборы в блокчейне CWD GLOBAL

Подобно большинству других блокчейнов, взаимодействие с блокчейнами CWD GLOBAL требует платы за использование его функций (т. е. операций). За каждую операцию взимается отдельная плата. Однако любой другой токен, зарегистрированный в блокчейне CWD GLOBAL, наряду с основным собственным токеном CWD может использоваться в качестве платы, если его управляющий решит поддержать это. С 11 августа 2023 действуют следющие значения комиссионных сборов:

<table><thead><tr><th width="77">№</th><th width="517">Операция</th><th>Сумма, CWD</th></tr></thead><tbody><tr><td>0</td><td>Перевод</td><td>6 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>600,00</td></tr><tr><td>1</td><td>Размещение ордера</td><td>6 000,00</td></tr><tr><td>3</td><td>Обновление залога</td><td>300,00</td></tr><tr><td>5</td><td>Создание аккаунта (обычный)</td><td>20,00</td></tr><tr><td></td><td>Создание аккаунта (премиум)</td><td>200 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>100,00</td></tr><tr><td>6</td><td>Обновление аккаунта (голосование, ключи)</td><td>300,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>150,00</td></tr><tr><td>7</td><td>Изменение списка доступа (черный и белый список)</td><td>450,00</td></tr><tr><td>8</td><td>Апгрейд аккаунта (годовое членство)</td><td>30 000,00</td></tr><tr><td></td><td>Апгрейд аккаунта (пожизненное членство, сервисный аккаунт)</td><td>150 000,00</td></tr><tr><td>9</td><td>Перевод аккаунта</td><td>75 000,00</td></tr><tr><td>10</td><td>Создать актив (3 символа)</td><td>75 000 000,00</td></tr><tr><td></td><td>Создать актив (4 символа)</td><td>45 000 000,00</td></tr><tr><td></td><td>Создать актив (5 и более)</td><td>3 750 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,010</td></tr><tr><td>11</td><td>Обновить актив</td><td>75 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,00100</td></tr><tr><td>12</td><td>Обновить SmartCoin актив</td><td>75 000,00</td></tr><tr><td>13</td><td>Обновить проставщиков котировок SmartCoin актива</td><td>75 000,00</td></tr><tr><td>14</td><td>Эмиссия актива</td><td>3 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>150,00</td></tr><tr><td>15</td><td>Сжечь актив</td><td>1,00</td></tr><tr><td>16</td><td>Пополнение пула комиссий актива</td><td>150,00</td></tr><tr><td>17</td><td>Запрос на погашение SmartCoin активов</td><td>150,00</td></tr><tr><td>18</td><td>Глобальное погашение SmartCoin активов</td><td>150,00</td></tr><tr><td>19</td><td>Публикация котировок SmartCoin активов</td><td>1,00</td></tr><tr><td>20</td><td>Создание заверителя</td><td>750 000,00</td></tr><tr><td>21</td><td>Обновление заверителя</td><td>3 000,00</td></tr><tr><td>22</td><td>Создание предложения (proposal)</td><td>1 500,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,0150</td></tr><tr><td>23</td><td>Обновление предложения (proposal)</td><td>1 500,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,0150</td></tr><tr><td>24</td><td>Удаление предложения (proposal)</td><td>150,00</td></tr><tr><td>25</td><td>Создание разрешения на вывод</td><td>150,00</td></tr><tr><td>26</td><td>Обновление разрешения на вывод</td><td>150,00</td></tr><tr><td>27</td><td>Истребование разрешения на вывод</td><td>1 500,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,015</td></tr><tr><td>29</td><td>Создание члена комитета</td><td>750 000,00</td></tr><tr><td>30</td><td>Обновление члена комитета</td><td>3 000,00</td></tr><tr><td>31</td><td>Обновление глобальных параметров Parametrs</td><td>150,00</td></tr><tr><td>32</td><td>Создание вестингового баланса</td><td>150,00</td></tr><tr><td>33</td><td>Вывод вестингового баланса</td><td>6 000,00</td></tr><tr><td>34</td><td>Создание работника</td><td>750 000,00</td></tr><tr><td>35</td><td>Специальная (произвольная) операция</td><td>10,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,0100</td></tr><tr><td>36</td><td>Операция подтверждения</td><td>150,00</td></tr><tr><td>38</td><td>Перевод актива эмитентом с аккаунта на аккаунт</td><td>300,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,015</td></tr><tr><td>39</td><td>Перевод на скрытый аккаунт</td><td>10,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,10</td></tr><tr><td>40</td><td>Скрытый перевод</td><td>10,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>0,10</td></tr><tr><td>41</td><td>Перевод со скрытого аккаунта</td><td>10,00</td></tr><tr><td>43</td><td>Взыскание комиссий с активов</td><td>3 000,00</td></tr><tr><td>48</td><td>Обновить эмитента актива</td><td>7 500,00</td></tr><tr><td>49</td><td>Апгрейд аккаунта (покупка контракта) - Start</td><td>750 000,00</td></tr><tr><td></td><td>Апгрейд аккаунта (покупка контракта) - Expert</td><td>4 500 000,00</td></tr><tr><td></td><td>Апгрейд аккаунта (покупка контракта) - Citizen</td><td>9 000 000,00</td></tr><tr><td></td><td>Апгрейд аккаунта (покупка контракта) - Infinity</td><td>15 000 000,00</td></tr><tr><td>55</td><td>Выставление лота</td><td>3 000,00</td></tr><tr><td>61</td><td>Сообщение</td><td>10,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>1,000</td></tr><tr><td>65</td><td>Создание объявления об обмене</td><td>60 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>6 000,00</td></tr><tr><td>66</td><td>Изменение объявления об обмене</td><td>6 000,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>600,00</td></tr><tr><td>67</td><td>Очистка блек-листа объявления</td><td>150,00</td></tr><tr><td>68</td><td>Удаление из блек-листа объявления</td><td>15,00</td></tr><tr><td>70</td><td>Отмена заявки на обмен</td><td>75,00</td></tr><tr><td>75</td><td>Успешное завершение сделки</td><td>300,00</td></tr><tr><td>78</td><td>Решение по заявке принято</td><td>3,00</td></tr><tr><td>82</td><td>Выплата по кредиту</td><td>300,00</td></tr><tr><td>83</td><td>Создание предложения о кредите</td><td>300,00</td></tr><tr><td>86</td><td>Дать под залог</td><td>300,00</td></tr><tr><td>87</td><td>Взять под залог</td><td>300,00</td></tr><tr><td>92</td><td>Обновление глобальных параметров Gamezone</td><td>15,00</td></tr><tr><td>93</td><td>Обновление глобальных параметров Staking</td><td>15,00</td></tr><tr><td>95</td><td>Стекинг Proof of Crowd</td><td>1 500 000,00</td></tr><tr><td>97</td><td>Обмен Silver на CWD</td><td>300,00</td></tr><tr><td>99</td><td>Перевод с арбитражем</td><td>10,00</td></tr><tr><td>104</td><td>Массовый платеж</td><td>500,00</td></tr><tr><td></td><td>Цена за килобайт</td><td>1,00</td></tr><tr><td>106</td><td>Смена наставника</td><td>50 000,00</td></tr><tr><td>107</td><td>Создание команды Большой Гонки</td><td>30 000,00</td></tr><tr><td>108</td><td>Удаление команды Большой Гонки</td><td>300,00</td></tr><tr><td>109</td><td>Отправка приглашения в команду</td><td>3 000,00</td></tr><tr><td>111</td><td>Удаление игрока из команды</td><td>300,00</td></tr><tr><td>112</td><td>Выход из команды</td><td>300,00</td></tr><tr><td>113</td><td>Голосование за параметры Большой Гонки</td><td>300,00</td></tr><tr><td>118</td><td>Ставка на рейтинг команды</td><td>150,00</td></tr><tr><td>119</td><td>Ставка на соревнование между командами</td><td>150,00</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td>Награда витнеса за создание блока</td><td>15,00</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td>Минимальные суммы открытия стекинга:</td><td></td></tr><tr><td></td><td>3 месяца</td><td>25 000,00</td></tr><tr><td></td><td>6 месяцев</td><td>25 000,00</td></tr><tr><td></td><td>12 месяцев</td><td>100 000,00</td></tr></tbody></table>

Предыдущие значения комиссий можно посмотреть в документе по ссылке: [https://cwdinfo.gitbook.io/library/](https://cwdinfo.gitbook.io/library/)

## Рабочий бюджет блокчейна CWD GLOBAL

Разница между максимальным объемом и оборотным объемом называется рабочим бюджетом и в прошлом часто называлась резервами. У блокчейна CWD GLOBAL есть ежедневный бюджет, который можно использовать для разработки. Этот бюджет имеет жестко заданный верхний предел общей суммы.

## Награда за производство блоков в блокчейне CWD GLOBAL

Производство блоков обусловлено расходами на эксплуатацию и техническое обслуживание оборудования. Блокчейн CWD GLOBAL признает этот факт, вознаграждая производителей блоков в основных токенах CWD за каждый произведенный блок. В зависимости от стоимости CWD комитет может изменить размер вознаграждения CWD за блок. По состоянию на 11 августа 2023 года каждый блок награждается 2 CWD. Эти CWD взяты из рабочего бюджета.

## Финансирование проекта («работники»)

Определенное количество ежедневно доступных токенов может быть выделено для разработки посредством «работников». Любой может создать «работника» в блокчейне CWD GLOBAL и запросить суточное вознаграждение в CWD. Если держатели CWD одобряют конкретного «работника», CWD переводятся из дневного бюджета. Гибкий лимит определяет максимальный размер дневного бюджета, который предоставляется всем утвержденным «работникам». Следовательно, те «работники», которые получили больше голосов от держателей CWD, получат свои средства первыми. Это означает, что «работники», даже если они утверждены, могутне получить финансирование при достижении вышеупомянутого порога. Кроме того, «работники» постоянно находятся под пристальным вниманием владельцев CWD, которые могут не одобрить (т. е. отозвать свой голос и «уволить») «работников», которые не выполняют свои обязанности.

## Вестинговый баланс

Вестинговые балансы содержат любые сборы, полученные, например, от стейкинга или через реферальную программу или заработную плату работника. У них есть определенный период начислений, и они постоянно разблокируются в течение этого периода, пока не будут доступны все балансы. Мы используем эту функциональность при получении дохода по стейкингу, так как доход распределяется в течение нескольких дней по разным стратегиям. Например, мы используем 6 месячный вид стейкинга, когда и первоначальный депозит монет и начисленные проценты освобождаются в конце срока стейкинга. При трехмесячном первоначальный депозит освобождается в конце срока, а сумма процентов равномерно размораживается. В годовых стейкингах проценты и тело суммируются и размораживаются ежесекундно в течение всего срока. Вестинговый баланс отображается в интерфейсе пользовательского аккаунта и его необходимо запросить в соответствующем разделе.

Vesting — это процесс начисления дохода, распределенный во времени по определенному графику.

## Консенсус

Консенсус — это процесс, посредством которого сообщество приходит к общепризнанному недвусмысленному соглашению по части информации.

В контексте блокчейнов консенсус означает согласие относительно правил действительности транзакций и порядка, в котором они соблюдаются блокчейном. В конечном итоге это приводит к соглашению о текущем состоянии, которое непреложно строится на основе этих правил действительности и последовательности транзакций.

Наиболее известная схема консенсуса — это Proof-of-Work (PoW). Самым доминирующим ее недостатком является высокое энергопотребление и масштабируемость с точки зрения количества транзакций в секунду и времени подтверждения. Блокчейн CWD GLOBAL использует алгоритм под названием Delegated Proof of Stake (DPoS), который был разработан специально для замены расточительного процесса майнинга, увеличения пропускной способности и сокращения времени реакции блокчейна. DPoS позволяет генерировать новый блок с фиксированной скоростью (время производства и подтверждения блока) с минимальными вычислительными требованиями. Это означает, что блокчейн может обрабатывать больше транзакций за значительно меньшее время и почти без затрат по сравнению с блокчейнами на основе PoW. Производство блоков осуществляется набором так называемых витнесов (производителей блоков), которые сменяют друг друга. После каждого цикла порядок производителей блоков определенным образом рандомизируется, так что все стороны соглашаются с новым порядком.

## Протокол

Самая важная часть технологий блокчейн здесь именуется протоколом блокчейн. Он определяет поведение всей системы, включая последствия и побочные эффекты при обработке транзакций. Пользователи используют определенные функции, создавая транзакцию, содержащую конкретное требование (также называемое операцией).

Поскольку блокчейн, как хранилище хранит только дополнительные изменения (например, переводы), окончательный баланс каждой учетной записи вместе с другой информацией необходимо отслеживать отдельно в текущем состоянии. Важно отметить, что протокол является определенным в том смысле, что одно и то же состояние генерируется при применении той же последовательности операций (как предусмотрено цепочкой блоков).

Это делает технологии блокчейн защищенными от несанкционированного доступа и поддающимися проверке.

В разработанном блокчейне CWD GLOBAL доступно более 90 операций (на начало 2022 года).

Каждая из них подключается к протоколу Blockchain как минимум три раза:

1. Проверка - во время проверки необработанные инструкции (также называемые полезной нагрузкой) проверяются на непротиворечивость. Например, в случае перевода мы гарантируем, что сумма перевода будет положительной.
2. Оценка - На этапе оценки конкретная операция — инструкция проверяется на соответствие текущему состоянию цепочки блоков. В случае перевода мы гарантируем, что переводимая сумма доступна на счету отправителя.
3. Применение - Hа этом этапе предпринимаются действия, изменяющие текущее состояние. В случае перевода мы уменьшаем баланс счета отправителя и увеличиваем баланс счета получателя в соответствии с количеством переданных токенов.

## Расширяемость

Программное обеспечение, лежащее в основе блокчейна CWD GLOBAL, имеет модульную структуру и выполняет свои операции независимо друг от друга. Это позволяет добавлять новые функции, когда соответствующий код, который реализует методы проверки, оценки и применения, становится полностью законченным.

В некотором смысле операции с блокчейном CWD GLOBAL представляют собой смарт-контракты и позволяют расширить набор функций системы. Однако в отличие от других платформ смарт-контрактов, CWD GLOBAL Blockchain требует, чтобы новые функции были проверены основными разработчиками и одобрены держателями CWD, прежде чем они могут быть установлены посредством обновления протокола в масштабе всей сети. Как следствие, платформа считается гораздо более надежной, поскольку новые функции требуют прохождения нескольких этапов контроля качества. Эти обновления протокола хорошо скоординированы и уже происходили 3 раза (на 4 квартал 2021 г.)

## Производительность и масштабируемость

Блокчейн BitShares публично продемонстрировал поддержку более 3000 (трех тысяч) транзакций в секунду и более 22000 операций в секунду в распределенной тестовой сети. Эта технология может легко масштабироваться до 100 000 (ста тысяч) и более транзакций в секунду с относительно простым улучшением производительности сервера и протоколов связи.

## Персонификация аккаунтов

Одной из интересных особенностей блокчейнов на базе Graphene/Bitshares являются именованные аккаунты, то есть в отличии от биткойна или этериума у вас есть не просто адрес кошелька, но и понятное название аккаунта, которое вы можете использовать при проведении транзакций.

CWD GLOBAL использует удобочитаемые имена учетных записей, которые должны быть зарегистрированы вместе с открытыми ключами в цепочке блоков перед их использованием. Таким образом, блокчейн действует как преобразователь имени и открытого ключа, аналогичный традиционной службе доменных имен (DNS). Эти именованные учетные записи позволяют пользователям легко запоминать и передавать информацию о своих учетных записях вместо использования подверженных ошибкам адресов. В зависимости от индивидуальных потребностей приложения, использующие блокчейн CWD GLOBAL, могут создавать дополнительное условие, которое имеет полную поддержку системы KYC (знай своего клиента) с помощью так называемого белого списка, который обеспечивает максимальный контроль и прозрачность, когда это необходимо.

В отличии от базового функционала Bitshares на платформе CWD GLOBAL разработан механизм защиты аккаунтов с помощью проверочного слова, который создается пользователем.

## Адресная книга

Для борьбы со скам-аккаунтами и различными фишинговыми схемами, а также для повышения удобства пользования платформой, был разработан полностью новый компонент — Адресная книга.

В адресную книгу можно добавлять те аккаунты, с которыми пользователь часто взаимодействует, можно добавлять понятные описания к этим аккаунтам, и проводить транзакции с ними буквально одной кнопкой, не вводя каждый раз название аккаунта. Функционал адресной книги довольно большой, начиная от переводов до поиска объявлений в CWDex от определенного аккаунта. Добавить аккаунт в адресную книгу можно или через строку поиска, или из интерфейса обзора аккаунта (новая кнопка будет рядом с кнопкой «отправить сообщение»).

Об адресной книге важно знать, что она хранится в браузере (local storage), поэтому если вы добавили кого-то в контакты на телефоне, то на компьютере этот контакт не появится. Для того чтобы перенести контакты с одного устройства на другое можно воспользоваться кнопками Импорт и Экспорт, которые в свою очередь загружают адресную книгу в IPFS. В IPFS адресная книга хранится 24 часа и при этом она никак не привязана ни к какому аккаунту.

Можно создавать белые списки, то есть адреса аккаунтов блокчейна, которые прошли проверку и вы уверены, что это ваш надежный партнер или черные списки адресов аккаунтов тех людей, которые себя в чем-то дискредитировали.

## Виды разрешений (авторизаций)

|              Ключ              |                                                                                                       Описание                                                                                                       |
| :----------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| Active key (Ключ прав доступа) |                                                              Данный ключ используется для подписания транзакций, которые не изменяют параметры аккаунта.                                                             |
|   Owner key (Ключ владельца)   |                             Данный ключ используется для внесения изменений в аккаунт. В случае взлома аккаунта, этот ключ необходим для изменения ключей, привязанных к учетной записи.                             |
|   Memo key (Ключ примечания)   | Данный ключ используется для шифрования дополнительной информации, передаваемой вместе с транзакцией. При использовании шифрования, этот текст будет доступен для чтения только отправителю и получателю транзакции. |

Блокчейн CWD GLOBAL создает разрешения для учетных записей, а не для криптографии, что упрощает использование.

Каждая учетная запись разделена на следующие типы разрешений:

Разрешение владельца - Это разрешение имеет административные полномочия для всей учетной записи и должно рассматриваться для стратегий «резервного копирования».

Активное разрешение - Позволяет получить доступ к средствам и некоторым настройкам учетной записи, но не может изменить разрешение владельца и, таким образом, считается «онлайн» разрешениями.

Полномочия состоят из одного или нескольких объектов, которые разрешают действие, такое как передача или обмен.

Полномочия состоят из одной или нескольких пар имени учетной записи с весом.

Чтобы получить действительную транзакцию, сумма весов от подписания сторон должна превышать порог, определенный в разрешениях.

Каждая учетная запись может контролироваться любой взвешенной комбинацией других учетных записей и закрытых ключей. Это создает иерархическую структуру, которая отражает то, как права организованы в реальной жизни, и делает многопользовательский контроль над средствами проще, чем когда-либо. Многопользовательский контроль является самым большим фактором безопасности, и при правильном использовании он может практически исключить риск кражи из-за взлома.

## Иерархия сети

Блокчейн CWD GLOBAL использует первую своем роде иерархическую систему закрытых ключей для облегчения использования обычных и резервных ключей. Обычные (активные) ключи предназначены для повседневного использования, в то время как отдельный резервный ключ (ключ владельца) может использоваться для восстановления доступа к учетной записи в случае потери обычных ключей. В идеале ключ владельца должен храниться в автономном режиме и использоваться только тогда, когда необходимо изменить ключи учетной записи или восстановить утерянный ключ. Большая часть программного обеспечения, поддерживающего блокчейн CWD GLOBAL, также облегчает использование мастер-пароля, который локально шифрует ключи клиента.

## Зашифрованные сообщения в блокчейне CWD GLOBAL

Учетная запись в блокчейне CWD GLOBAL имеет связанный с ней так называемый открытый ключ записи, который позволяет инициировать зашифрованную связь между двумя сторонами с помощью общего секрета, полученного с помощью алгоритма Диффи-Хеллмана на эллиптической кривой. Это позволяет прикреплять зашифрованные сообщения к передачам токенов, которые могут расшифровать только отправитель и получатель.

Отправка зашифрованных сообщений на блокчейне CWD GLOBAL — платная и стоимость зависит от длины сообщения.

## Реферальная программа

Блокчейн CWD GLOBAL имеет интегрированную восьмиуровневую реферальную систему, в отличии от одноуровневой системы BitShares. Более подробно условия участия в реферальной программе рассмотрены в [соответствующем разделе](vidy-dokhoda-na-platforme-cwd-global/aktivnyi-dokhod-na-platforme-cwd.global/sistema-vyplaty-referalnykh-voznagrazhdenii.md).

## Комиссионные сборы в блокчейне CWD GLOBAL

Подобно большинству других блокчейнов, взаимодействие с блокчейнами CWD GLOBAL требует платы за использование его функций (т. е. операций). За каждую операцию взимается отдельная плата. Однако любой другой токен, зарегистрированный в блокчейне CWD GLOBAL, наряду с основным собственным токеном CWD может использоваться в качестве платы, если его управляющий решит поддержать это.

## Рабочий бюджет блокчейна CWD GLOBAL

Разница между максимальным объемом и оборотным объемом называется рабочим бюджетом и в прошлом часто называлась резервами. У блокчейна CWD GLOBAL есть ежедневный бюджет, который можно использовать для разработки. Этот бюджет имеет жестко заданный верхний предел общей суммы.

## Награда за производство блоков в блокчейне CWD GLOBAL

Производство блоков обусловлено расходами на эксплуатацию и техническое обслуживание оборудования. Блокчейн CWD GLOBAL признает этот факт, вознаграждая производителей блоков в основных токенах CWD за каждый произведенный блок. В зависимости от стоимости CWD комитет может изменить размер вознаграждения CWD за блок. По состоянию на 15 мая 2023 года каждый блок награждается 1 CWD. Эти CWD взяты из рабочего бюджета.

## Финансирование проекта («работники»)

Определенное количество ежедневно доступных токенов может быть выделено для разработки посредством «работников». Любой может создать «работника» в блокчейне CWD GLOBAL и запросить суточное вознаграждение в CWD. Если держатели CWD одобряют конкретного «работника», CWD переводятся из дневного бюджета. Гибкий лимит определяет максимальный размер дневного бюджета, который предоставляется всем утвержденным «работникам». Следовательно, те «работники», которые получили больше голосов от держателей CWD, получат свои средства первыми. Это означает, что «работники», даже если они утверждены, могут не получить финансирование при достижении вышеупомянутого порога. Кроме того, «работники» постоянно находятся под пристальным вниманием владельцев CWD, которые могут не одобрить (т. е. отозвать свой голос и «уволить») «работников», которые не выполняют свои обязанности.

## Вестинговый баланс

Вестинговые балансы содержат любые сборы, полученные, например, от стейкинга или через реферальную программу или заработную плату работника. У них есть определенный период начислений, и они постоянно разблокируются в течение этого периода, пока не будут доступны все балансы.

Мы используем эту функциональность при получении дохода по стейкингу, так как доход распределяется в течение нескольких дней по разным стратегиям. Например, мы используем 6 месячный вид стейкинга, когда и первоначальный депозит монет и начисленные проценты освобождаются в конце срока стейкинга.

При трех-месячных и годовых стейкингах проценты и тело суммируются и размораживаются ежесекундно в течение всего срока. Вестинговый баланс отображается в интерфейсе пользовательского аккаунта и его необходимо запросить в соответствующем разделе.

Vesting — это процесс начисления дохода, распределенный во времени по определенному графику.

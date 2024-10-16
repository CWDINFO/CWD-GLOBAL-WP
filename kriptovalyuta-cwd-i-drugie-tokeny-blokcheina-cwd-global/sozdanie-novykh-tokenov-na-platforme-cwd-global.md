# Создание новых токенов на платформе CWD GLOBAL

Являясь инструментом инвестиционного децентрализованного сообщества, Платформа CWD GLOBAL позволяет предпринимателям экосистемы выпускать собственные токены для развития собственных направлений бизнеса.

Основные настройкиОсновные настройкиВыпустить собственный токен может любой активный член сообщества CWD GLOBAL, используя для этого только интерфейс своего личного кабинета.

Для создания собственного токена необходимо произвести апгрейд аккаунта.

Чтобы произвести апгрейд, необходимо активировать кнопку «Сервисный аккаунт» на главной странице.

Операция апгрейда до сервисного аккаунта платная, и составляет 150 000 CWD. После апгрейда в основном меню появится новый пункт — Активы.

В этом разделе можно выпускать новые токены и управлять уже выпущенными.

## Выпуск нового токена

Для создания нового актива, нужно нажать кнопку «Создать актив». Откроется раздел создания актива, который состоит из четырёх вкладок:

{% tabs %}
{% tab title="Основные настройки" %}
В нём нужно указать желаемое название валюты. Комиссия за короткие имена 3 символа составляет 75 000 000 CWD, 4 символа - 45 000 000 CWD, за выпуск токена с названием от 5 символов комиссия составит 3 750 000 CWD, половину из которой можно будет вернуть после выпуска токена.

Затем нужно указать максимальное количество актива, т.к. основное свойство криптовалют — это их ограниченность. Далее нужно указать количество знаков после запятой, от этого зависит будет ли токен делимым или будет продаваться и переводиться только целиком.

Следующий шаг — понятие «Основной обменный курс». Эмитент может разрешить пользователям оплачивать системную комиссию при помощи своего токена, но только при условии, что сам заплатит эту комиссию в базовой валюте CWD с помощью механизма обменного пула. Этот функционал нужен только в редких случаях, поэтому разработчик не рекомендует использовать его без особой необходимости. Просто укажите какое-нибудь большое число в поле Количество основного актива (например, 100000).

#### Smart-Coin

Следующая опция переключатель Smart-Coin. Это специальный механизм, который позволяет выпускать стейбл коины и различные инструменты для рынка бинарных прогнозов.

Данный механизм требует отдельной инфраструктуры, и как показала практика Вitshares, эти инструменты не очень актуальны, поэтому в большинстве случаев этот переключатель остается выключенным. Поэтому в интерфейсе платформы CWD GLOBAL механизм smart-coin также пока не поддерживается.
{% endtab %}

{% tab title="Описание" %}
Содержит общую информацию о выпускаемом токене и функциях, которые он выполняет. А также указывает предпочтительную пару для биржевых торгов. Разработчик всегда рекомендуем указывать здесь CWD. Вся информация, указанная данном разделе, видна всем другим пользователям.
{% endtab %}

{% tab title="Права доступа" %}
Два визуально похожих раздела, однако у них разная суть.

В разделе права доступа необходимо указать, какие опции для данного токена могут быть активированы после его выпуска. То есть это возможность в будущем использовать указанные здесь функции. После того как токен выпущен, вы не сможете добавить новые права доступа, вы сможете только отключить уже имеющиеся. Но сами функции, указанные в этих правах (при условии, что права активированы), вы можете включать и отключать в любое время, редактируя актив. Например, вы можете использовать рыночную комиссию или разрешить владеть токенами только тем, кто находится в белом списке токена. По умолчанию рекомендуем включать все значения на вкладке Права доступа.
{% endtab %}

{% tab title="Маркеры" %}
И, напротив, отключать все значения на вкладке Маркеры, чтобы добавлять нужные значения при необходимости.
{% endtab %}
{% endtabs %}

После того как все поля заполнены нужно нажать кнопку «Создать актив» и подтвердить транзакцию. Теперь актив создан и появится в аккаунте создателя разделе Активы.

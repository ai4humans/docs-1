---
editable: false
---

# Правила тарификации для {{ mrd-name }}

{% include [currency-choice](../_includes/pricing/currency-choice.md) %}

{% include [pricing-status.md](../_includes/mdb/pricing-status.md) %}


## Из чего складывается стоимость использования {{ mrd-short-name }} {#rules}

Расчет стоимости использования {{ mrd-name }} учитывает:

{% include [pricing-rules](../_includes/mdb/pricing-rules.md) %}

{% include [pricing-gb-size](../_includes/pricing-gb-size.md) %}


### Использование хостов БД {#rules-hosts-uptime}

Стоимость начисляется за каждый час работы хоста в соответствии с выделенными для него вычислительными ресурсами. Поддерживаемые конфигурации ресурсов приведены в разделе [{#T}](concepts/instance-types.md), цены за использование vCPU и RAM — в разделе [Цены](#prices).

Минимальная единица тарификации — час (например, стоимость 1,5 часов работы хоста равна стоимости 2 часов). Время, когда хост {{ RD }} не может выполнять свои основные функции, не тарифицируется.


### Использование дискового пространства {#rules-storage}

Оплачивается:

* Объем диска, выделенный для кластеров БД.

* Объем, занимаемый резервными копиями баз данных сверх запрошенного размера дисков для кластера.

    * Резервные копии хранятся бесплатно, пока сумма размера БД и всех резервных копий остается меньше выбранного объема хранилища.
    * Запрошенный размер диска выделяется для каждого хоста, поэтому количество хостов кластера не влияет на объем хранилища и, соответственно, на бесплатный объем резервных копий.

Цена указывается за 1 месяц использования. Минимальная единица тарификации — 1 ГБ в час (например, стоимость хранения 1 ГБ в течение 1,5 часов равна стоимости хранения в течение 2 часов).


## Цены {#prices}


### Вычислительные ресурсы хостов {#prices-hosts}

Ресурс | Цена за 1 час, вкл. НДС
----- | -----
5% vCPU (**burstable**, 2 ГБ RAM) | 0,01 ₽
20% vCPU (**burstable**, 4 ГБ RAM) | 0,23 ₽
100% vCPU (**high-memory**) | 1,25 ₽
RAM (за 1 ГБ) | 0,34 ₽


### Хранилище и резервные копии {#prices-storage}

Услуга | Цена за ГБ в месяц, вкл. НДС
----- | -----
Быстрое сетевое хранилище  | 8,1356 ₽ |
Резервные копии сверх размера хранилища  | 2,5424 ₽


### Исходящий трафик {#prices-traffic}

{% include notitle [pricing-egress-traffic](../_includes/pricing/pricing-egress-traffic.md) %}


## Расчетные цены для конфигураций хостов {#calculated-prices}

Цены за время работы хостов рассчитаны исходя из [конфигураций хостов](concepts/instance-types.md) и приведенных выше цен за использование RAM. Чтобы точно рассчитать стоимость нужного кластера, воспользуйтесь [калькулятором](https://cloud.yandex.ru/services/managed-redis#calculator).

{% include [host-class-price-alert](../_includes/mdb/pricing-host-class-alert.md) %}

{% list tabs %}

- За месяц работы хоста

  Из расчета 720 часов в месяц, округлено до целых рублей.

  RAM, ГБ | Цена за месяц, вкл. НДС
  ----- | -----
  **burstable** |
  2 | 504 ₽
  4  | 1 310 ₽
  **high-memory** |
  8 | 3 758 ₽
  12 | 4 738 ₽
  16 | 5 717 ₽
  24 | 9 475 ₽
  32 | 11 434 ₽
  48 | 15 350 ₽
  64 | 19 267 ₽
  80 | 23 184 ₽
  96 | 30 701 ₽
  128 | 38 534 ₽
  160 | 46 368 ₽
  192 | 54 202 ₽
  224 | 62 035 ₽
  256 | 69 869 ₽

- За 1 час работы хоста

  RAM, ГБ | Цена за час, вкл. НДС
  ----- | -----
  **burstable** |
  2 | 0,70 ₽
  4 | 1,82 ₽
  **high-memory** |
  8 | 5,22 ₽
  12 | 6,58 ₽
  16 | 7,94 ₽
  24 | 13,16 ₽
  32 | 15,88 ₽
  48 | 21,32 ₽
  64 | 26,76 ₽
  80 | 32,20 ₽
  96 | 42,64 ₽
  128 | 53,52 ₽
  160 | 64,40 ₽
  192 | 75,28 ₽
  224 | 86,16 ₽
  256 | 97,04 ₽

{% endlist %}

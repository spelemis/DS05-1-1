# Day 05 – Введение в машинное обучение
## Оглавление
1. [Глава I](#глава-i) \
    1.1. [Преамбула](#преамбула)
2. [Глава II](#глава-ii) \
    2.1. [Общая инструкция](#общая-инструкция)
3. [Глава III](#глава-iii) \
    3.1. [Цели](#цели) 
4. [Глава IV](#глава-iv) \
    4.1. [Задание](#задание)
5. [Глава V](#глава-v) \
    5.1. [Сдача работы и проверка](#сдача-работы-и-проверка)

## Глава I
### Преамбула
Наверное, тебе встречалось довольно много разных терминов из сферы анализа данных: искусственный интеллект, 
машинное обучение, нейронные сети, глубокое обучение. Но чем отличаются друг от друга все эти термины и отличаются ли они вообще?
На самом деле каждый последующий термин из этого списка является подмножеством предыдущего. 
То есть самый широкий термин из всех перечисленных — искусственный интеллект. Он включает в себя любые техники и 
алгоритмы, которые способны имитировать человеческое поведение. Это могут быть алгоритмы машинного обучения, 
а могут быть просто правила, написанные на любом языке программирования в духе “if-then-else”.

Например, еще в 1966 году был создан виртуальный собеседник Элиза, которая имитировала диалог с психотерапевтом. 
В большинстве случаев она просто перефразировала то, что говорил человек. В некоторых случаях она находила ключевые 
слова, к которым были привязаны специальные реплики. Несмотря на то, что в программе не использовалось никаких 
нейронных сетей или алгоритмов машинного обучения, её можно считать вариантом искусственного интеллекта. 
Та же современная Алиса от Яндекса отчасти построена на тех же принципах и правилах, хотя уже и использует алгоритмы
машинного обучения.


![d05_elisa](misc/images/elisa.png)

Что же такое машинное обучение? Машинное обучение включает в себя статистические алгоритмы, которые автоматизируют 
процесс создания этих самых правил: их больше не надо прописывать вручную. Например, обученная модель способна сама 
распознавать эмоциональное состояние человека по реплике. Реплики могут быть разными, содержать множество разных 
ключевых слов, но модель способна почти во всех из них определить правильно эмоциональную окраску и соответствующим образом среагировать.
Подмножеством алгоритмов машинного обучения являются нейронные сети. Создатели этих алгоритмов вдохновлялись тем, 
как устроен человеческий мозг (но тем не менее нейронные сети достаточно далеки от полного подобия).

А подмножеством нейронных сетей являются алгоритмы deep learning (глубокого обучения). Это тоже нейронные сети, но обладающие 
большим количеством слоев (большим количеством уровней иерархии). По этой причине они называются «глубокими».

![d05_fields](misc/images/fields.png)

## Глава II
### Общая инструкция

Методология Школы 21 может быть не похожа на тот образовательный опыт, который случался с тобой ранее. Её отличает высокий уровень автономии: у тебя есть задача, ты должен её выполнить. По большей части тебе нужно будет самому добывать знания для её решения. Второй важный момент — это peer-to-peer обучение. В образовательном процессе нет менторов и экспертов, перед которыми ты защищаешь свой результат. Ты это делаешь перед таким же учащимися, как и ты сам. У них есть чек-лист, который поможет им качественно выполнить приемку вашей работы.

Роль Школы 21 заключается в том, чтобы обеспечить через последовательность заданий и оптимальный уровень поддержки такую траекторию обучения, при которой ты не только освоишь hard skills, но и научишься самообучаться.

- Не доверяй слухам и предположениям о том, как должно быть оформлено ваше решение. Этот документ является единственным источником, к которому стоит обращаться по большинству вопросов;
- твое решение будет оцениваться другими учащимися;
- подлежат оцениванию только те файлы, которые ты выложил в GIT (ветка develop, папка src);
- в твоей папке не должно быть лишних файлов — только те, что были указаны в задании;
- не забывай, что у вас есть доступ к интернету и поисковым системам;
- обсуждение заданий можно вести и в Rocket.Chat;
- будь внимателен к примерам, указанным в этом документе — они могут иметь важные детали, которые не были оговорены другим способом;
- и да пребудет с тобой Сила!

## Глава III
### Цели

Этот проект может быть сложным для понимания. Мы непосредственно подошли к предиктивному анализу, в центре которого 
лежат алгоритмы машинного обучения. Под капотом у них заложена серьезная математика, в которую мы сейчас не будем сильно вдаваться:
чтобы ездить на автомобиле, совсем необязательно знать, как устроен двигатель внутреннего сгорания. 
При этом мы хотим заложить в материал моменты, которые могли бы продемонстрировать интуицию того, как эти алгоритмы примерно работают.

## Глава IV
### Задание

Машинное обучение можно разделить на две части: с учителем и без учителя. В обучении с учителем ты хочешь что-то предсказать. 
Ты передаешь машине наблюдения: смотри, что происходило (признаки, `X`), и к чему это приводило (целевая переменная, `y`). 
Ты говоришь ей: а теперь попробуй найти здесь какие-то закономерности между признаками и целевой переменной. 
Алгоритм ищет эти закономерности и упаковывает их в виде модели: так или иначе это некоторые коэффициенты при значениях признаков.

В обучении с учителем есть две больших задачи: классификация и регрессия. Классификация — это задача, в которой ты 
пытаешься спрогнозировать значение *категориальной* целевой переменной (пол, тип двигателя, город),
регрессия — в которой она *непрерывная* (температура, зарплата, стоимость).

Датасет этого проекта [здесь](https://nextcloud-test.nsk.21-school.ru/s/xjnsG5p26MaYMHB).

Перед тобой стоит задача классификации. Тебе нужно научиться прогнозировать отток клиентов - уйдет клиент от нас в ближайшее время или нет. 
У тебя есть какие-то данные о них, и известно, кто из них в прошлом ушел из банка, а кто остался клиентом. 
Алгоритм, глядя на эти данные, должен найти закономерности и создать модель.

Мы попробуем использовать различные модели машинного обучения. Про их устройство мы будем более подробно говорить в следующих проектах.  
Помимо этого тебе нужно будет померить качество этой модели. 
Для этого разбей свой датасет на две части: обучающую выборку (`train`) и тестовую (`test`). 
На обучающей выборке алгоритм будет учиться, а на тестовой ты проверишь его реальную точность на тех примерах, 
которые алгоритм не видел. Ведь суть построения модели заключается в том, чтобы она дальше встроилась в один из 
процессов банка и прогнозировала отток по текущим клиентам, а они еще пока не ушли, но часть из них может это сделать.
Но перед этим тебе придется еще поработать с предобработкой данных. Алгоритмы машинного обучения в этом смысле бывают достаточно привередливыми.

Теперь более подробно.

### Task 1
Назначь колонку `ID` индексом таблицы. После выведите 5 первых строк таблицы.

### Task 2
Определимся что является нашим `X`, а что является нашим `Y`. \
Для этого изучи документ, описывающий наш [датасет](datasets/data_description.docx). \
Признаки сохрани в переменную `X`. Целевую переменную, которую мы будем предсказывать, в переменную `Y`.  \
Выведи размерность этих таблиц.

### Task 3
Наши признаки содержат в себе как количественные, так и категориальные переменные. Разделим признаки. \
В этом поможет тип данных колонки. Категориальные переменные сохрани в переменную `X_cat`, а количественные в `X_num`. \
Выведи число категориальных и количественные переменных.

### Task 4
Предобработаем количественные переменные. Проведите стандартизацию для признаков X_num. \
Сохрани результат стандартизации в переменную `X_num_scal`. \
Выведи среднее и стандартное отклонение по датасету для каждого признака после стандартизации. \
Значения округли для сотых.

### Task 5
Алгоритмы машинного обучения плохо работают с категориальными признаками, поэтому их надо трансформировать. \
Прочитай про One-Hot Encoding подход к кодированию и примени его с нашим категориальным признакам, сохрани 
результат в переменную `X_cat_ohe`. Перед этим удали признак `CLNT_JOB_POSITION` (у него слишком много значений). \
Выведи количество колонок таблицы `X_cat_ohe`

### Task 6
Объедини 2 предобработанных датасета. Результат запиши в переменную `X_ready`. Сохрани датасет в папку `datasets/data_prepared.csv`. \
Подели получившийся датасет на `train` и `test`. Процент тестовой выборки: `20%`. Используй параметр `random_state=21`. \
Выведи размерность обучающей выборки X_train.

### Task 7
Обучи логистическую регрессию с параметрами: `solver='liblinear'`, `fit_intercept=False`, `penalty='l1'`, `random_state=21`. \
Посчитай `accuracy` модели на тестовой выборке, сравнив предсказанные значения с реальными. \
Выведи значение `accuracy` модели на тестовой выборке.

### Task 8
Посчитай процент клиентов в тестовой выборке, у которых индикатор оттока равен `0`, и сравнить с `accuracy`. \
Тебе что-то должно показаться подозрительным)

### Task 9
Построй график, на котором видны топ-10 самых важных факторов по мнению модели в абсолютном значении. \
В этом тебе поможет функция [feature_importanse](code-samples/feature_importanse.py).

Дополнительные ресурсы для обучения мы привели в файле [reading_list.md](materials/reading_list.md). \
Если же ты хочешь поделиться с сокурсниками еще какими-либо полезными материалами по теме - **смело пиши их в чат проекта!**


## Глава V
### Сдача работы и проверка
Сохрани решение в файле 05-assignment.ipynb. Загружать промежуточные файлы не требуется! \
Загрузи изменения на Git в ветку develop.

💡 [Нажми здесь](https://forms.gle/4D2DmM49qxWLE4Ch8) **чтобы отправить обратную связь по проекту**. 

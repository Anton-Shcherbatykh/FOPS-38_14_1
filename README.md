## Домашнее задание к занятию «Ветвления в Git» Щербатых А.Е. FOPS-38

### Задание «Ветвление, merge и rebase» 

**Шаг 1.** Создал каталог branching и файлы merge.sh и rebase.sh

![alt text](Pictures/Pic02.jpg)

#### Подготовка файла merge.sh
**Шаг 1.** Создал ветку ```git-merge```

![alt text](Pictures/Pic03.jpg)

**Шаг 2.** Заменил в ней содержимое файла ```merge.sh``` согласно заданию

**Шаг 3.** Создал коммит "merge: @ instead *" и запушил изменения в репозиторий

![alt text](Pictures/Pic04.jpg)

**Шаг 4.** Вношу ещё одни изменения в файл ```merge.sh```

**Шаг 5.** Создаю коммит ```merge: use shift``` и отправляю изменения в репозиторий:

![alt text](Pictures/Pic05.jpg)

#### Изменим ```main```

**Шаг 1.** Вернулся в ветку ```main```. (команда отражена на скрине в следующем шаге)

**Шаг 2.** Изменил содержимое файла rebase.sh

![alt text](Pictures/Pic05_1.jpg)

**Шаг 3.** Отправил изменения в ветку main:

![alt text](Pictures/Pic06.jpg)

#### Подготовка файла rebase.sh

**Шаг 1.** С помощью команды git log нахожу хеш коммита ```prepare for merge and rebase``` и выполняю ```git checkout``` на него:

![alt text](Pictures/Pic07.jpg)

![alt text](Pictures/Pic08.jpg)

![alt text](Pictures/Pic09.jpg)

**Шаг 2.** Создаю ветку git-rebase, основываясь на текущем коммите

**Шаг 3.** Изменяю содержимое файла ```rebase.sh``` согласно задания

**Шаг 4.** Отправляю эти изменения в ветку ```git-rebase``` с комментарием ```git-rebase 1```.

![alt text](Pictures/Pic010.jpg)

**Шаг 5.** Сделал ещё один коммит ```git-rebase 2``` с пушем, заменив ```echo "Parameter: $param"``` на ```echo "Next parameter: $param"```

![alt text](Pictures/Pic011.jpg)

#### Промежуточный итог

Проверил, что у меня получилось на network странице по ссылке [FOPS-38_14/network](https://github.com/Anton-Shcherbatykh/FOPS-38_14_1/network)

![alt text](Pictures/Pic012.jpg)

#### Merge
Переключаюсь на ветку ```main```. Сливаю ветку ```git-merge``` в ```main``` и отправляю изменения в репозиторий

![alt text](Pictures/Pic013.jpg)

Результат тут [FOPS-38_14/network](https://github.com/Anton-Shcherbatykh/FOPS-38_14_1/network)

#### Rebase
**Шаг 1.** и **Шаг 2.** Выполнил rebase ветки git-rebase на main, создав конфликт:

![alt text](Pictures/Pic014.jpg)

Смотрю содержимое файла rebase.sh и вижу метки, оставленные Git для решения конфликта:

![alt text](Pictures/Pic015.jpg)

**Шаг 3.** Удаляю метки, выбираю вариант echo "$@ Parameter #$count = $param"

**Шаг 4.** Сообщаю Git, что конфликт решён и продолжаю rebase.

![alt text](Pictures/Pic016.jpg)

Шаг 5 и 6 пропущен, т.к. конфликт был разрешён

**Шаг 7.** Пытаюсь выполнить пуш и вижу, что команда завершается с ошибкой:

![alt text](Pictures/Pic017.jpg)

Это происходит потому, что я пытаюсь перезаписать историю.

**Шаг 8.** Пытаюсь выполнить пуш с флагом force и это удается сделать:

![alt text](Pictures/Pic018.jpg)

**Шаг 9.** Смержу ветку git-rebase в main простой перемоткой:

![alt text](Pictures/Pic019.jpg)

Проверил, что у меня получилось на network странице по ссылке [FOPS-38_14/network](https://github.com/Anton-Shcherbatykh/FOPS-38_14_1/network)

# Лабораторная работа №2
**Part1**

   1) Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).

   2) Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
```bash
Команда: echo "# lab2" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:amirparag2005/lab2.git
git push -u origin main

Вывод:подсказка: Using 'main' as the name for the initial branch. This default branch name
подсказка: is subject to change. To configure the initial branch name to use in all
подсказка: of your new repositories, which will suppress this warning, call:
подсказка: 
подсказка: 	git config --global init.defaultBranch <name>
подсказка: 
подсказка: Names commonly chosen instead of 'main' are 'main', 'trunk' and
подсказка: 'development'. The just-created branch can be renamed via this command:
подсказка: 
подсказка: 	git branch -m <name>
Инициализирован пустой репозиторий Git в /home/amir/other/lab2/.git/
[main (корневой коммит) a8eff7e] first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 216 байтов | 72.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To github.com:amirparag2005/lab2.git
 * [new branch]      main -> main
Ветка «main» отслеживает внешнюю ветку «main» из «origin».
```
   
   
   3) Создайте файл hello_world.cpp в локальной копии репозитория (который должен был появиться на шаге 2).
    Реализуйте программу Hello world на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку using namespace std;.
```bash
Команда:nano hello_world.cpp

Код:
#include <iostream>
using namespace std;
int main(){

cout << "hello world!" << endl;

return 0;
}




```
    
   4) Добавьте этот файл в локальную копию репозитория.
```bash
Команда:git add hello_world.cpp

```
   
   5) Закоммитьте изменения с осмысленным сообщением.
```bash
Команда:git commit -m "Added initial version of hello_world.cpp"

Вывод:[main d578368] Added initial version of hello_world.cpp
 1 file changed, 12 insertions(+)
 create mode 100644 hello_world.cpp
```
   
   6) Изменитьте исходный код так, чтобы программа через
    стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение Hello world from @name, где @name имя пользователя.
```bash
Код:
#include <iostream>
#include <string>
using namespace std;
int main(){
string name;
cout << "Input your name: ";
cin >> name;

cout << "hello world from " << name << endl;

return 0;
}
```
    
   7) Закоммитьте новую версию программы. Почему не надо добавлять файл повторно git add?
   
   Не нужно добавлять файл повторно `git add` перед коммитом изменений, потому что при использовании опции `-a` ("--all") в команде `git commit`, Git автоматически добавляет все измененные файлы в коммит 
   
```bash
Команда: git commit -a -m "new version of hello_world.cpp. Added name usage"

Вывод: [main f531113] new version of hello_world.cpp. Added name usage
 2 files changed, 103 insertions(+), 3 deletions(-)
```
  
   8) Запуште изменения в удалёный репозиторий.
```bash
Команда: git push origin main

Вывод:Перечисление объектов: 9, готово.
Подсчет объектов: 100% (9/9), готово.
При сжатии изменений используется до 6 потоков
Сжатие объектов: 100% (7/7), готово.
Запись объектов: 100% (7/7), 2.12 КиБ | 2.13 МиБ/с, готово.
Всего 7 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To github.com:amirparag2005/lab2.git
   a8eff7e..14526bd  main -> main
```
   
   9) Проверьте, что история коммитов доступна в удалёный репозитории.
   

**Part2**

  1)  В локальной копии репозитория создайте локальную ветку patch1.
```bash
Команда: git checkout -b patch1
Вывод: Switched to a new branch 'patch1'
```
  
   2) Внесите изменения в ветке patch1 по исправлению кода и избавления от using namespace std;
```bash
Код: 
#include <iostream>
#include <string>

int main(){
std::string name;
std::cout << "Input your name: ";
std::cin >> name;

std::cout << "hello world from " << name << std::endl;

return 0;
}
```
   
   3) commit, push локальную ветку в удалённый репозиторий.
```bash
Команда:git add hello_world.cpp
Команда:git commit -m "Removed using namespace std;"
Вывод:[patch1 49316c5] Removed using namespace std;
 1 file changed, 9 insertions(+), 9 deletions(-)
 
Команда:git push origin patch1
Вывод:Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 6 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 425 байтов | 425.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/amirparag2005/lab2/pull/new/patch1
remote: 
To github.com:amirparag2005/lab2.git
 * [new branch]      patch1 -> patch1
```
   
   4) Проверьте, что ветка patch1 доступна в удалёный репозитории.
   
   5) Создайте pull-request patch1 -> main.
Создаем pull-request по ссылке из пункта 3:
```bash
https://github.com/amirparag2005/lab2/compare/patch1
```
   
   6) В локальной копии в ветке patch1 добавьте в исходный код комментарии.
```bash
Код: 
#include <iostream>
#include <string>

int main(){
std::string name;
//Name input
std::cout << "Input your name: ";
std::cin >> name;

std::cout << "hello world from " << name << std::endl;

return 0;
}
```
   
   7) commit, push.
```bash
Команда: git commit -a -m "Added comments to the code"
Вывод:[patch1 e2a27b7] Added comments to the code
 2 files changed, 231 insertions(+), 35 deletions(-)


Команда:git push origin patch1
Вывод:Перечисление объектов: 7, готово.
Подсчет объектов: 100% (7/7), готово.
При сжатии изменений используется до 6 потоков
Сжатие объектов: 100% (4/4), готово.
Запись объектов: 100% (4/4), 3.23 КиБ | 1.61 МиБ/с, готово.
Всего 4 (изменений 1), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To github.com:amirparag2005/lab2.git
   f531113..e2a27b7 patch1 -> patch1
```
   
   8) Проверьте, что новые изменения есть в созданном на шаге 5 pull-request
Проверяем в удаленном репозитории через графический интерфейс гитхаб
   
   9) В удалённый репозитории выполните слияние PR patch1 -> main и удалите ветку patch1 в удаленном репозитории.
   Через графический интерфейс выполняем слияние
```bash
Команда: git branch -d patch1
Вывод:Ветка patch1 удалена (была e2a27b7).
```
   
   10) Локально выполните pull.
```bash
Команда: git pull origin main
Вывод:remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Распаковка объектов: 100% (1/1), 933 байта | 933.00 КиБ/с, готово.
Из github.com:amirparag2005/lab2
 * branch            main       -> FETCH_HEAD
   14526bd..1b9c832  main       -> origin/main
Обновление 14526bd..1b9c832
Fast-forward
 README.md       | 257 ++++++++++++++++++++++++++++++++++++++++++++++++-------
 hello_world.cpp |  19 ++--
 2 files changed, 236 insertions(+), 40 deletions(-)

```
   
   11) С помощью команды git log просмотрите историю в локальной версии ветки main.
```bash
Команда: git log
Вывод:commit 1b9c8328f345b595c3601f3520267cc9783060e1 (HEAD -> main, origin/main)
Merge: 14526bd ecb2d9c
Author: Amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 19:40:53 2024 +0300

    Merge pull request #1 from amirparag2005/patch1
    
    Removed using namespace std;

commit ecb2d9cbbcabbe9b402db1882b57d5e5796d098e (patch1)
Author: amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 19:24:30 2024 +0300

    Added comments to the code

commit 49316c5923b3fcaeb9102e1dc89b39c873040775
Author: amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 19:16:47 2024 +0300

    Removed using namespace std;

commit 14526bd00b440ccd65c4ffe2929166ba2682670b
Author: amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 19:04:06 2024 +0300

    new version of hello_world.cpp. Added name usage

commit 6ea83849a6112c7eed4fb19aefbd665d17fbfc93
Author: amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 19:01:28 2024 +0300

    Added initial version of hello_world.cpp with bad coding style.

commit a8eff7e6b64d58f360a1bae2268cb03d106f68d3
Author: amir <amirparag2022@mail.ru>
Date:   Thu Apr 18 18:19:38 2024 +0300

    first commit

```
   
   12) Удалите локальную ветку patch1.
```bash
Команда: git branch -d patch1
Вывод: Deleted branch patch1 (was e2a27b7).

```


**Part3**

   1)Создайте новую локальную ветку patch2.
```bash
Команда: git checkout -b patch2

Вывод: Switched to a new branch 'patch2'
```
    
   2) Измените code style с помощью утилиты clang-format. Например, используя опцию -style=Mozilla.
```bash
Команда: clang-format -style=Mozilla -i hello_world.cpp
```
   
   3) commit, push, создайте pull-request patch2 -> main.
```bash
Команда: git add hello_world.cpp

Команда:git commit -m "Updated code style using clang-format"
Вывод:[patch2 ebad822] Updated code style using clang-format
 1 file changed, 10 insertions(+), 10 deletions(-)
```
   
   4) В ветке main в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
Изменяем через графический интерфейс комментарий на русский язык
   
   5) Убедитесь, что в pull-request появились конфликтны.
Пулл реквест пишет, что merge невозможен, у нас конфликт
   
   6) Для этого локально выполните pull + rebase (точную последовательность команд, следует узнать самостоятельно). Исправьте конфликты.
   
```bash
Команда: git pull origin main
Вывод:remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Распаковка объектов: 100% (3/3), 1016 байтов | 63.00 КиБ/с, готово.
Из github.com:amirparag2005/lab2
 * branch            main       -> FETCH_HEAD
   1b9c832..42518aa  main       -> origin/main
Обновление 1b9c832..42518aa
Fast-forward
 hello_world.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

Команда:git checkout patch2
Вывод:Переключились на ветку «patch2»

Команда:git add .

Команда:git commit -m "Commit message here"
Вывод:[patch2 3cad08d] Commit message here
 1 file changed, 150 insertions(+), 45 deletions(-)
 
Команда:git rebase main
Вывод:Автослияние hello_world.cpp
КОНФЛИКТ (содержимое): Конфликт слияния в hello_world.cpp
error: не удалось применить коммит ebad822... Updated code style using clang-format
подсказка: Resolve all conflicts manually, mark them as resolved with
подсказка: "git add/rm <conflicted_files>", then run "git rebase --continue".
подсказка: You can instead skip this commit: run "git rebase --skip".
подсказка: To abort and get back to the state before "git rebase", run "git rebase --abort".
Не удалось применить коммит ebad822... Updated code style using clang-format

Команда:git add .

Команда:git rebase --continue
Вывод:[отделённый HEAD 503fef6] Updated code style using clang-format
 1 file changed, 2 deletions(-)
Успешно перемещён и обновлён refs/heads/patch2.
```
Тут мы исправили конфликт через Visual studio Code оставив настоящие изменения
   
   7) Сделайте force push в ветку patch2
```bash
Команда: git push origin patch2 --force

Вывод:Перечисление объектов: 9, готово.
Подсчет объектов: 100% (9/9), готово.
При сжатии изменений используется до 6 потоков
Сжатие объектов: 100% (6/6), готово.
Запись объектов: 100% (6/6), 2.51 КиБ | 514.00 КиБ/с, готово.
Всего 6 (изменений 2), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To github.com:amirparag2005/lab2.git
 + ebad822...03ab391 patch2 -> patch2 (forced update)
```
   
   8) Убедитель, что в pull-request пропали конфликтны.
Пулл реквест зеленый, значит, можно вливать ветку patch2
   
   9) Вмержите pull-request patch2 -> main.
Через графический интерфейс мержим вторую ветку в главную.
```
git merge patch2 main
```

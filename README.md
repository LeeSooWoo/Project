# Project
## Работа в Git 

### Команды
#### Навигация

* pwd (от англ. print working directory, «показать рабочую папку») — покажи, в какой я папке;
* ls (от англ. list directory contents, «отобразить содержимое директории») — покажи файлы и папки в текущей папке;
* ls -a — покажи также скрытые файлы и папки, названия которых начинаются с символа .;
* cd first-project (от англ. change directory, «сменить директорию») — перейди в папку first-project;
* cd first-project/html — перейди в папку html, которая находится в папке first-project;
* cd .. — перейди на уровень выше, в родительскую папку;
* cd ~ — перейди в домашнюю директорию (/Users/Username);
* cd / — перейди в корневую директорию.

---
#### Работа с файлами и папками
##### Создание
touch index.html (англ. touch, «коснуться») — создай файл index.html в текущей папке;
touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
mkdir second-project (от англ. make directory, «создать директорию») — создай папку с именем second-project в текущей папке.
Копирование и перемещение
cp file.txt ~/my-dir (от англ. copy, «копировать») — скопируй файл в другое место;
mv file.txt ~/my-dir (от англ. move, «переместить») — перемести файл или папку в другое место.
##### Чтение
cat file.txt (от англ. concatenate and print, «объединить и распечатать») — распечатай содержимое текстового файла file.txt.
##### Удаление
rm about.html (от англ. remove, «удалить») — удали файл about.html;
rmdir images (от англ. remove directory, «удалить директорию») — удали папку images;
rm -r second-project (от англ. remove, «удалить» + recursive, «рекурсивный») — удали папку second-project и всё, что она содержит.
##### Полезные возможности
Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&).
У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑) и вниз (↓).
Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.

##### Репозитарий 

Сделать папку репозиторием — git init
Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием (от англ. repository — «хранилище»). Для этого следует переместиться в неё и ввести команду git init (от англ. initialize — «инициализировать»).

Команда git add позволяет подготовить файл к сохранению.
Команда git add --all подготовит к сохранению сразу все файлы.
С помощью git add . можно добавить в репозиторий текущую папку со всеми файлами.

---

##### Git и платформы для удалённой работы


Git и GitHub — это два разных проекта, которые развиваются независимо друг от друга. 
Git:
- консольный инструмент для работы с локальными и удалёнными репозиториями;
- проект с открытым исходным кодом.
GitHub:
- платформа для размещения удалённых репозиториев;
- принадлежит компании Microsoft.
Кроме GitHub, есть и другие платформы для командной работы. Например, GitLab и Bitbucket, которые тоже позволяют работать с Git. У каждой из этих платформ свои особенности и дополнительная функциональность:
- GitLab можно развернуть в виде сервера в приватной сети;
- Bitbucket — продукт компании Atlassian, поэтому он легко интегрируется с другими инструментами этой компании, такими как Jira.

SSH — протокол, который обеспечивает безопасный обмен данными в сети и использует для этого ключи.
SSH-ключ — ваш виртуальный идентификатор в GitHub. Как ключ от квартиры, он позволяет получить доступ к GitHub-репозиторию. Также SSH используется для доступа к другим удалённым серверам.
SSH-ключ состоит из двух частей — публичной и приватной. Публичный ключ зашифрует данные, а приватный — расшифрует. Приватным ключом ни в коем случае нельзя делиться, иначе любой сможет расшифровать все ваши секреты!

ls -a ~/.ssh Эта команда покажет содержимое папки .ssh.
ls -la ~/.ssh Эта команда покажет содержимое папки .ssh в виде списка файлов.

скопировать содержимое ключа в буфер обмена:
$ clip < ~/.ssh/id_rsa.pub
для ed25519:
$ clip < ~/.ssh/id_ed25519.pub

origin (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один). Это значительно упрощает работу.

Отправить изменения на удалённый репозиторий — git push

Вы уже прошли весь «цикл коммита»: подготовили файлы с помощью git add, закоммитили их с комментарием командой git commit -m. Осталось загрузить содержимое локального репозитория на GitHub. За это отвечает команда git push (от англ. push — «толкать»).
В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.
$ git push -u origin main # Если команда приведёт к ошибке, попробуйте # заменить main на master.

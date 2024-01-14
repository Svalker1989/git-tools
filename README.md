В клонированном репозитории:  
* Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.  
Ответ:  
`git show aefea`  
Полный хеш  
aefead2207ef7e2aa5dc81a34aedf0cad4c32545  
Комментарий:  
Update CHANGELOG.md  
Ответьте на вопросы:  
* Какому тегу соответствует коммит 85024d3?  
Ответ:  
`git show 85024d3`  
v0.12.23  
* Сколько родителей у коммита b8d720? Напишите их хеши.
  Ответ:  
  `git show b8d720^2`  
  2 родителя. Подобрал перебором цифр после крышечки  
* Перечислите хеши и комментарии всех коммитов, которые были сделаны между тегами v0.12.23 и v0.12.24.  
  Ответ:  
  `git log v0.12.23..v0.12.24 --graph`  
  ![](https://github.com/Svalker1989/git-tools/blob/main/Z.PNG)  
* Найдите коммит, в котором была создана функция func providerSource, её определение в коде выглядит так: func providerSource(...) (вместо троеточия перечислены аргументы).  
  Сначала нашел в каком файле определена функция через `git grep 'providerSource'`. Файл - provider_source.go   
  Далее командой `git log -L :providerSource:provider_source.go` нашел какие изменения происходили в теле фонкции. Самое раннее определение было в коммите:  
  8c928e83589d90a031f811fae52a81be7153e82f  

* Найдите все коммиты, в которых была изменена функция globalPluginDirs.  
  Аналогично предыдущему заданию, сначала нашел файл с функцией `git grep 'globalPluginDirs'`. Файл - plugins.go.  
  Далее командой `git log -L :globalPluginDirs:plugins.go` нашел какие изменения происходили в теле фонкции. Коммиты:  
  78b12205587fe839f10d946ea3fdc06719decb05  
  52dbf94834cb970b510f2fba853a5b49ad9b1a46  
  41ab0aef7a0fe030e84018973a64135b11abcd70  
  66ebff90cdfaa6938f26f908c7ebad8d547fea17  
  8364383c359a6b738a436d1b7745ccdce178df47  
 
* Кто автор функции synchronizedWriters?  
  Удалось только найти кто удалил функцию из кода.  
  Сначала командой нашел в каких коммитах были изменения этой функции `git log -SsynchronizedWriters --oneline` 
  Пройдя по всем коммитам с помощью `git show`, смог найти, что в коммите 5ac311e2a91e381e2f52234668b49ba670aa0fe5 функция была добавлена автором Martin Atkins.  
В качестве решения ответьте на вопросы и опишите, как были получены эти ответы.


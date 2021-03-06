# Консольный Текстовый редактор vim
vi (vim) — это один из самых популярных консольных текстовых редакторов. Что значит консольный текстовый редактор? Это значит, что у него нет графического интерфейса, как например у того же текстового редактора Microsoft Word и.т.д.

Vim — это улучшенный клон vi. Vim (от «vi improved» — «улучшенный vi») содержит различные улучшения, визуальные подсказки и хорошую справочную систему.

В Debian по умолчанию установлен vi, но он немного не удобен, для того чтоб установить vim нужно:
```
apt install vim
```

Vim есть несколько режимов работы:

* обычный — режим навигации по тексту;
* вставки — режим ввода текста (краткосрочный);
* командный — режим для ввода команд;
* поиска — режим для поиска и замены;
* визуальный — режим выделения текста;

При входе в файл вы по умолчанию оказываетесь в командном режиме и редактор ждет от вас ввода команд. Команды позволяют перемещаться по файлу, производить определенные правки, переходить в режим вставки, для того чтобы добавить новый текст. Команды так же нужны для выхода из файла(с сохранением или без), чтобы вернуться в командную строку UNIX.
Эти два режима можно рассматривать как две абсолютно разные клавиатуры, в режиме вставки ваша клавиатура работает в режиме печатной машинки, в командном режиме почти каждая клавиша имеет свое назначение или вызывает какую либо инструкцию.

### Переход в режим вставки:


| Клавиша            | режим              |                                                                                                                                     
|:-------------:|:-------------:|  
|  i |  перейти в режим ввода с текущей позиции |     
|  I |  переместиться в начало строки и перейти в режим ввода |     
|  a |  вставить текст справа от текущего символа |     
|  A |  вставить текст в конец текущей строки |     
|  o |  перейти в режим ввода с новой строки под курсором |     
|  O |  перейти в режим ввода с новой строки над курсором |     

### Клавиши поиска:


| Клавиша            | режим              |                                                                                                                                             
|:-------------:|:-------------:|  
| /<pattern> | перейти к <pattern>;
| / | повторить поиск;
| ?<text> | то же самое, но искать назад;
| n | повторить поиск;
| N | повторить поиск назад;
| * | перейти к следующему вхождению слова под курсором (создаётся шаблон поиска слова вида: «/\<word\>»);
| # | перейти к предыдущему вхождению слова под курсором (создаётся шаблон поиска слова вида: «?\<word\>»);
| [I  | найдет и покажет количество вхождений слова (функции) под курсором (будет создан список строк, содержащих слово).

### Работа с файлами

| Команда       | действия      |                                                                                                                                             
|:-------------:|:-------------:|  
|:w         |	Записать файл
|:w <имя файла>|	Записать файл и задать ему имя
|:q!	|Выйти из редактирования без сохранения изменений
|:wq	|Выйти и сохранить
|:x	|Выйти и сохранить короткий вариант
  
  
### Горячие клавиши vim
  
| Клавиша           | Действие   |                                                                                                                                             
|:-------------:|:-------------:|                                                                                                                                             
|h	            | Влево                                                                                                                                                       |
|l	            | Вправо                                                                                                                                                      |
|j	            | Вниз                                                                                                                                                        |
|k	            | Вверх                                                                                                                                                       |
|w	            | Вперед на первую букву слова                                                                                                                                |
|e	            | Вперед на последнюю букву слова                                                                                                                             |
|b	            | Назад на первую букву слова                                                                                                                                 |
|ge	            | Назад на последнюю букву слова                                                                                                                              |
|W	            | То, же, что и w, но словом считается то, что отделено пустыми символами                                                                                     |
|E	            | То, же, что и e, но словом считается то, что отделено пустыми символами                                                                                     |
|B	            | То, же, что и b, но словом считается то, что отделено пустыми символами                                                                                     |
|gE	            | То, же, что и ge, но словом считается то, что отделено пустыми символами                                                                                    |
|^	            | На первый непустой символ строки                                                                                                                            |
|$,End	        | На конец строки                                                                                                                                             |
|0,Home	        | На начало строки                                                                                                                                            |
|(	            | На первую точку слева от курсора (если она есть, в противном случае на начало абзаца)                                                                       |
|)	            | На первую точку справа от курсора (если она есть, в противном случае на конец абзаца)                                                                       |
|{	            | На абзац назад до пустой строки                                                                                                                             |
|}	            | На абзац вперед до пустой строки                                                                                                                            |
|gj	            | На одну экранную строку вниз. Экранная строка — это целая строка длиной меньше ширины экрана, либо часть длинной строки, разделенной на экране на несколько |
|gk	            | На одну экранную строку вверх.                                                                                                                              |
|f#	            | Поиск вперед в строке символа # и установка курсора на него                                                                                                 |
|F#	            | Поиск назад в строке символа # и установка курсора на него                                                                                                  |
|t#	            | Поиск вперед в строке символа # и установка курсора после него                                                                                              |
|T#	            | Поиск назад в строке символа # и установка курсора после него                                                                                               |
|;	            | Повтор поиска вперед символа, найденного при помощи f/t/F/T                                                                                                 |
|,	            | Повтор поиска назад символа, найденного при помощи f/t/F/T                                                                                                  |
|%	            | Перемещение курсора на скобку, парную той, на которой находится курсор. Парные символы можно задать при помощи команды :set matchpairs                      |
|:#	            | Перемещение курсора на строку #                                                                                                                             |
|#G	            | Перемещение курсора на строку #, аналогично :#                                                                                                              |
|gg	            | Перемещение курсора в начало                                                                                                                                |
|G	            | Перемещение курсора в конец                                                                                                                                 |
|#%	            | Перемещение курсора на # процентов от начала                                                                                                                |
|H	            | Перемещение курсора на начало видимой части текста                                                                                                          |
|M	            | Перемещение курсора на середину видимой части текста                                                                                                        |
|L	            | Перемещение курсора на конец видимой части текста                                                                                                           |
|Control+u	    | На полэкрана вверх                                                                                                                                          |
|Control+d	    | На полэкрана вниз                                                                                                                                           |
|Control+y	    | На одну строку вверх. Курсор при этом не перемещается                                                                                                       |
|Control+e	    | На одну строку вниз. Курсор при этом не перемещается                                                                                                        |
|Control+b	    | На один экран минус 2 строки вверх                                                                                                                          |
|Control+f	    | На одну экран минус 2 строки вниз                                                                                                                           |
|zt	            | Прокрутка текста так, чтобы курсор оказался вверху экрана                                                                                                   |
|zz	            | Прокрутка текста так, чтобы курсор оказался в середине экрана                                                                                               |
|zb	            | Прокрутка текста так, чтобы курсор оказался внизу экрана                                                                                                    |

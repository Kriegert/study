Постановка задачи:
Необходимо написать программу, исправляющую орфографические ошибки в поисковых запросах. Программа должна уметь обрабатывать файлы со статистикой, принимать на вход файл со списком запросов и формировать файл со списком исправленных запросов. Также, при запуске программы должны обрабатываться следующие ключи:

./prog learn --input [input file] --output [stats file]
./prog correct --stats [stats file] --input [input file] --output [output file]

Где [input file] – путь до входного файла с запросами, [stats file] – файл со статистикой, [output file] – выходной файл.
Метод решения:

Решение поставленной задачи состоит из трёх основных этапов:
1. Построения дерева (trie), которое хранит все орфографически правильные слова.
2. Построения для каждого слова из запроса списка слов с расстоянием Левенштейна меньшим или равным двум.
3. Применения алгоритма Витерби для получения наиболее вероятной исправленной последовательности.

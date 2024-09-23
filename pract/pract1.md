Практическое занятие №1. Введение, основы работы в командной строке

Задача 1:
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).

localhost:~# grep '.*' /etc/passwd | cut -d: -f1 | sort

![image](https://github.com/user-attachments/assets/b6989411-5b23-436d-b100-76b57abc670e)


Задача 2:
Вывести данные /etc/protocols в отформатированном и отсортированном порядке для 5 наибольших портов

localhost:~# awk '{print $2, $1}' /etc/protocols | sort -nr | head -n 5

![image](https://github.com/user-attachments/assets/4961cec3-1cce-45b9-a0df-391999859716)

Задача 3:
Написать программу banner средствами bash для вывода текстов (размер баннера должен меняться!).

nano banner.sh
#!/bin/bash
text=$*
length=${#text}
for i in $(seq 1 $((length + 2))); do
    line+="-"
done
echo "+${line}+"
echo "| ${text} |"
echo "+${line}+"
chmod +x banner.sh
./banner.sh "Hello from RTU MIREA!"

![image](https://github.com/user-attachments/assets/45a72109-e143-4459-bc00-4a686a958d23)

![image](https://github.com/user-attachments/assets/b9aa48a0-e3bb-44b9-9f93-7b1f511b532a)

Задача 4:
Написать программу для вывода всех идентификаторов (по правилам C/C++ или Java) в файле (без повторений).

#!/bin/bash
file="$1"
id=$(grep -o -E '\b[a-zA-Z]*\b' "$file" | sort -u)
echo "Идентификаторы:"
echo "$id"

![image](https://github.com/user-attachments/assets/5f7e631e-f603-4142-b20b-41a12c86601c)

![image](https://github.com/user-attachments/assets/0299bb08-40c0-4f74-bfa4-c00b1b21e513)


Задача 5:
Написать программу для регистрации пользовательской команды (правильные права доступа и копирование в /usr/local/bin).

![image](https://github.com/user-attachments/assets/3717ec0c-89a9-4e52-8082-352e7604ce40)

![image](https://github.com/user-attachments/assets/0638295b-d063-4f72-9088-a2316b5a9e14)

Задача 6:
Написать программу для проверки наличия комментария в первой строке файлов с расширением c, js и py.

![image](https://github.com/user-attachments/assets/8ae2776d-77d0-4221-a505-c866e992ce3b)

![image](https://github.com/user-attachments/assets/4534bdcc-9d1b-4909-9e88-b41d60aa4f04)

![image](https://github.com/user-attachments/assets/1cdc2877-b651-41ff-b372-7e8768a441f6)

Задача 7:
Написать программу для нахождения файлов-дубликатов (имеющих 1 или более копий содержимого) по заданному пути (и подкаталогам).

![image](https://github.com/user-attachments/assets/0f15db95-497a-4f05-9a89-b130a5d29e79)


Задача 8:
Написать программу, которая находит все файлы в данном каталоге с расширением, указанным в качестве аргумента и архивирует все эти файлы в архив tar.

![image](https://github.com/user-attachments/assets/e372f946-7c73-4839-9847-56ee440d15f5)

![image](https://github.com/user-attachments/assets/a38f47e4-0c84-4e33-b147-1fbe9f5bee8c)

Задача 9:
Написать программу, которая заменяет в файле последовательности из 4 пробелов на символ табуляции. Входной и выходной файлы задаются аргументами.

![image](https://github.com/user-attachments/assets/5e326883-790f-47cb-8f12-3f33b5904c0b)

![image](https://github.com/user-attachments/assets/c396a2a7-e1b2-4ecd-b22d-0e9ea5f7aff9)

![image](https://github.com/user-attachments/assets/49169a2c-3ad1-42de-8bda-aa50bf33909e)

Задача 10:
Написать программу, которая выводит названия всех пустых текстовых файлов в указанной директории. Директория передается в программу параметром.

![image](https://github.com/user-attachments/assets/a6a5ce73-02fa-4fe6-9e8e-6010797cc5e3)

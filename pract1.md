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

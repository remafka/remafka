#!/bin/bash

**есть ли 2 параметра?*** 
if [ "$#" -ne 2 ]; then
    echo "Usage: $0 <input_directory> <output_directory>"
    exit 1

***вывести, если меньше параметров, чем планировалось*** 
fi

***есть ли входная директория?*** 
if [ ! -d "$1" ]; then
    echo "Input directory does not exist"
    exit 1
    
***если входной директории нет*** 
fi

***создадим выходную директорию, если её нет*** 
mkdir -p "$2"

***копируем файлы из входной дир. в выходную дир.*** 
find "$1" -type f -exec cp {} "$2" \;

***тест о завершении*** 
echo "Files copied successfully from $1 to $2"

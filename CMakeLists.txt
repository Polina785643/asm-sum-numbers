cmake_minimum_required(VERSION 3.10)

# Указываем что проект не использует C/C++
project(asm_sum_numbers NONE)

# Простая цель для сборки ассемблерной программы
add_custom_target(sum_numbers ALL
    COMMAND nasm -f elf64 sum_numbers.asm -o sum_numbers.o
    COMMAND ld -no-pie sum_numbers.o -o sum_numbers
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    COMMENT "Сборка программы на ассемблере"
)

# Цель для очистки с другим именем
add_custom_target(clean_all
    COMMAND rm -f sum_numbers sum_numbers.o
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}
    COMMENT "Очистка объектных и исполняемых файлов"
)

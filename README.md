cd ~/asm-sum-numbers
cat > README.md << 'EOF'
# ASM Sum Numbers

Программа на ассемблере для сложения двух чисел с использованием системных вызовов Linux x86-64.

## Описание
Программа запрашивает два числа с клавиатуры, вычисляет их сумму и выводит результат.

## Сборка и запуск

### Способ 1: CMake
```bash
mkdir build
cd build
cmake ..
make
cd ..          # возврат в корневую директорию
strace -o strace.log ./sum_numbers  # запуск программы с strace
make clean_all # удаляем бинарные файлы

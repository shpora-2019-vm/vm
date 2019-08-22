# VirtualMachine

## SimpleAssembler
Компилятор программ, написанных на языке ассемблер, созданном для этой машины
Примеры программ:
1. Echo: [hello.sasm](VirtualMachine.SimpleAssembler/hello.sasm)
2. Вечный цикл [incrementer.sasm](VirtualMachine.SimpleAssembler/incrementer.sasm)
### Использование:
#### Вывести список инструкций: 
- `VirtualMachine.SimpleAssembler` **[DLL с набором инструкций]**
- `VirtualMachine.SimpleAssembler VirtualMachine.CPU.InstructionSet.dll`
#### Собрать программу:
- `VirtualMachine.SimpleAssembler` **[DLL с набором инструкций] [файл с исходным кодом] [файл с программой]**
- `VirtualMachine.SimpleAssembler VirtualMachine.CPU.InstructionSet.dll hello.sasm hello.xs1` 

## Runner
Виртуальная машина, исполняющая скомпилированные программы (`.xs1`)
Файл конфигурации: [vm.json](VirtualMachine.Runner/vm.json)
### Использование
- `VirtualMachine.Runner` **[файл с скомпилированной программой]**
- `VirtualMachine.Runner hello.xs1`
  
## Debugger.Client.Console
Консольный отладчик приложений, написанных для виртуальной машины
### Использование
#### Запуск:
- `VirtualMachine.Debugger.Client.Console`
#### Пример использования:
1. `connect` - подключение к отладчику запущенного Runner-а
   - `localhost` (хостнейм, который слушает дебаггер (по-умолчанию))
   - `31337` (порт, который слушает дебаггер (по-умолчанию))
2. `paused` - проверить, что приложение приостановлено (только когда оно приостановлено его можно отлаживать)
3. `mode-set` - сменить режим отладки
   - `Stepping` - режим пошаговой отладки
4. `mem-read` - прочитать оперативную память программы
   -  `0` -  начиная с нулевого адреса
   -  `40` - прочитать 40 слов (одно слово = 4 байта)



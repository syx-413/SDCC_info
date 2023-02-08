# SDCC command line options

Created: February 6, 2023 12:02 AM

### 芯片参数（处理器选项）

1. `mmcs51`（默认）生成Intel MCS51系列的执行码。
2. `mgbz80`生成GameBoy Z80处理器的执行码。
3. `mpic14`生成Microchip 14位系列的执行码。
4. `mpic16`生成Microchip 16位系列的执行码。

### 前置處理器參數 (Preprocessor Options)

1. 1. -I<path>
2. D<macro[=value]>

### 链接器参数（Linker 选项）

1. `L --lib-path <绝对路径到额外的库>`
2. `-xram-loc <Value>` 
   
    外部存储器的起始位置，预设值为 0，值可以用十进位或 16 进位，如 `--xram-loc 0x8000` 或`--xram-loc 32768`。
    
3. `-code-loc <Value>` 
   
    程序存储器的起始位置，预设值为 0，值可以用十进位或 16 进位，如 `--xram-loc 0x8000` 或 `--xram-loc 32768`。
    
4. `-out-fmt-ihx`（预设）
   
    产生 IntelHex 格式的烧写档案。
    
5. `-out-fmt-s19` 
   
    产生 Motorola S19 格式的烧写档案。
    
6. `-out-fmt-elf` 
   
    产生 ELF 格式的执行档案。
    

### MCS51 参数 (MCS51 Options)

1. `-model-medium`
2. `-model-large`
3. `-xstack`
4. `-iram-size <Value>` 
   
    设置内部存储器(internal ram) 大小，默认值 256。
    
5. `-xram-size <Value>` 
   
    设置外部存储器(external ram) 大小，默认值 64K。
    
6. `-code-size <Value>`
   
    设置程序存储器 (code memory) 大小，默认值 64K。
    
7. `-stack-size <Value>` 
   
    设置堆栈 (stack) 大小。
    
8. `-pack-iram (default)`
9. `-no-pack-iram`
10. `-acall-ajmp`

### 最佳化參數 (Optimization Options)

1. `-no-xinit-opt` 
   
    不要复制代码的初始数据到xdata。当没有任何初始数据时，可以使用此选项来减少代码大小。
    
2. `-nooverlay` 
   
    传递参数和局部变量不要重叠使用，这样可能会增加内存损耗，但可以保证程序不出问题。
    
3. `-opt-code-speed`
   
     编译出最快的执行文件，执行文件会变大。
    
4. `-opt-code-size` 
   
    编译出最小的执行文件，执行文件会变慢。
    

### 其他参数 (Other Options)

1. `c --compile-only` 
   
    只进行编译，不进行链接，不生成烧录文件。
    
2. `E` 
   
    只执行预处理器，并将结果显示到标准输出即屏幕上。
    
3. `-stack-auto`
   
    所有的函数都被编译成可重复进入 (reentrant) 的函数。
    
4. `-Werror` 
   
    把所有的警告当作错误。
    
5. `-print-search-dirs` 
   
    显示编译器的默认搜索路径。
    
6. `-vc` 
   
    使用 MSVC 样式来显示警告及错误，默认是使用 GCC 样式。
    
7. `-std-sdcc89`
   
     (default) 使用 C89 标准，并允许 SDCC 的扩展指令。
    
8. `-std-c89` 
   
    使用 C89 标准，不允许 SDCC 的扩展指令。
    
9. `-std-sdcc99` 
   
    使用 C99 标准，并允许 SDCC 的扩展指令。
    
10. `-std-c99` 
    
    使用 C99 标准，不允许 SDCC 的扩展指令。
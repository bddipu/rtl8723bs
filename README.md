build command:
make ARCH=arm -C /path/to/kernel/build/folder

for the error,
"usr/bin/ld: scripts/dtc/dtc-parser.tab.o:(.bss+0x10): multiple definition of 'yylloc'; scripts/dtc/dtc-lexer.lex.o:(.bss+0x0): first defined here"

edit the file "/scripts/dtc/dtc-lexer-lex.c"  inside the build folder of linux kernel source 
Find the line 'YYLTYPE yylloc' and change it to 'extern YYLTYPE yylloc'

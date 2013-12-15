# ソースファイルが複数ある場合のMakefile

# 単純でバカな記述例
# なぜバカかというと、func.cだけをいじったばあいにmain.cがコンパイルされてしまうから。
hello: func.c main.c
	gcc -Wall -O2 -o hello func.c main.c

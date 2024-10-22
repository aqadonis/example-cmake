cmake_minimum_required(VERSION 3.28)
project(ListCommand)

set(CMAKE_CXX_STANDARD 20)

add_executable(ListCommand main.cpp)

set(MY_LIST 1 3 5 4 2 5 6 6 6 2 11 23 56 4 3 12)
# 13542566621123564312
message(${MY_LIST})
# 1;3;5;4;2;5;6;6;6;2;11;23;56;4;3;12
message("${MY_LIST}")

list(LENGTH MY_LIST MY_LIST_LEN)
# 16
message(${MY_LIST_LEN})

list(GET MY_LIST 3 VAL1)
# 4
message(${VAL1})

list(APPEND MY_LIST 5 5 54 56 24)
# 1;3;5;4;2;5;6;6;6;2;11;23;56;4;3;12;5;5;54;56;24
message("${MY_LIST}")

list(SORT MY_LIST)
# 1;11;12;2;2;23;24;3;3;4;4;5;5;5;5;54;56;56;6;6;6
message("${MY_LIST}")

list(REMOVE_DUPLICATES MY_LIST)
# 1;11;12;2;23;24;3;4;5;54;56;6
message("${MY_LIST}")

list(REVERSE MY_LIST)
# 6;56;54;5;4;3;24;23;2;12;11;1
message("${MY_LIST}")

list(GET MY_LIST 0 1 3 6 MY_LIST_2)
# 6;56;5;24
message("${MY_LIST_2}")

list(JOIN MY_LIST +-+ MY_LIST_STR)
# 6+-+56+-+54+-+5+-+4+-+3+-+24+-+23+-+2+-+12+-+11+-+1
message(${MY_LIST_STR})

list(SUBLIST MY_LIST 2 2 MY_LIST_3)
# 54;5
message("${MY_LIST_3}")

list(SUBLIST MY_LIST 4 -1 MY_LIST_3)
# 4;3;24;23;2;12;11;1
message("${MY_LIST_3}")

list(INSERT MY_LIST 3 100 101)
# 6;56;54;100;101;5;4;3;24;23;2;12;11;1
message("${MY_LIST}")

list(POP_BACK MY_LIST)
# 6;56;54;100;101;5;4;3;24;23;2;12;11
message("${MY_LIST}")

list(POP_BACK MY_LIST AA1 AA2)
# 11 12
message(${AA1} " " ${AA2})
# 6;56;54;100;101;5;4;3;24;23;2
message("${MY_LIST}")

list(POP_FRONT MY_LIST AA1 AA2)
# 6 56
message(${AA1} " " ${AA2})
# 54;100;101;5;4;3;24;23;2
message("${MY_LIST}")

list(PREPEND MY_LIST AA1 AA2)
# AA1;AA2;54;100;101;5;4;3;24;23;2
message("${MY_LIST}")

list(APPEND MY_LIST 22 22 22 23 33)
# AA1;AA2;54;100;101;5;4;3;24;23;2;22;22;22;23;33
message("${MY_LIST}")
list(REMOVE_ITEM MY_LIST 22)
# AA1;AA2;54;100;101;5;4;3;24;23;2;23;33
message("${MY_LIST}")

list(REMOVE_AT MY_LIST 3)
# AA1;AA2;54;101;5;4;3;24;23;2;23;33
message("${MY_LIST}")

list(REMOVE_AT MY_LIST 0 1)
# 54;101;5;4;3;24;23;2;23;33
message("${MY_LIST}")

list(SORT MY_LIST COMPARE NATURAL ORDER DESCENDING)
# 101;54;33;24;23;23;5;4;3;2
message("${MY_LIST}")

message("---------")

set(LIST01 a s d f g h j k l q w e)
list(TRANSFORM LIST01 TOUPPER FOR 3 5)
# asdFGHjklqwe
message(${LIST01})
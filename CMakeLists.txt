CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

ADD_SUBDIRECTORY(googletest)

SET(CMAKE_CXX_STANDARD 11)

ADD_EXECUTABLE(main
    main.cpp
    LibraryFacade.cpp
    Media.cpp
    Book.cpp
    Category.cpp
    BookManager.cpp
    User.cpp
    owedDebts.cpp
)

ADD_EXECUTABLE(main2
    main2.cpp
    Media.cpp
    Book.cpp
    Category.cpp
    BookManager.cpp
)

ADD_EXECUTABLE(test
    unit_test.cpp
    Media.cpp
    Book.cpp
    Category.cpp
    BookManager.cpp
    User.cpp
    owedDebts.cpp
)

TARGET_LINK_LIBRARIES(
    test
    gtest 
)

TARGET_COMPILE_DEFINITIONS(test PRIVATE gtest_disable_pthreads=ON)
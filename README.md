# 🐈 blnscpp
Single header C++ API for the Big List of Naughty Strings https://github.com/minimaxir/big-list-of-naughty-strings

Here's some examples:
```
Powerلُلُصّبُلُلصّبُررً ॣ ॣh ॣ ॣ冗
🏳0🌈️
జ్ఞ‌ా
گچپژ
Ω≈ç√∫˜µ≤≥÷
åß∂ƒ©˙∆˚¬…æ
œ∑´®†¥¨ˆøπ“‘
¡™£¢∞§¶•ªº–≠
¸˛Ç◊ı˜Â¯˘¿
ÅÍÎÏ˝ÓÔÒÚÆ☃
Œ„´‰ˇÁ¨ˆØ∏”
```

# Example Usage
```c++
#include "blns.h"
#include <iostream>

auto blns = blns::Blns{};
for (auto const &ns : blns.getStrings()) {
    std::cout << ns << "\n";
}
```

# CMake Integration

You can setup your CMake project to use BLNS using [CPM](https://github.com/cpm-cmake/CPM.cmake)
(no need to download / clone this repo manually):

```cmake
project("myapp")
add_executable(${PROJECT_NAME} myapp.cpp)

CPMAddPackage("gh:Teskann/blnscpp#master")  # Add this after add_executable / add_library, ...

target_include_directories(${PROJECT_NAME} PRIVATE ${blnscpp_SOURCE_DIR}/include)  # Add include path
target_link_libraries(${PROJECT_NAME} PRIVATE lib_blns)  # Link the blns library
```

With this setup, you can use blns like so in `myapp.cpp`:

```c++
#include <blns/blns.h>  // <-- Blns header to include
#include <iostream>

int main() {
    auto blns = blns::Blns{};
    for (auto const &ns : blns.getStrings()) {
        std::cout << ns << "\n";
    }
}
```
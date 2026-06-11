# MyBigNumber - Phép cộng hai số nguyên lớn

Module C++ thực hiện phép cộng hai số nguyên lớn (biểu diễn dưới dạng `std::string`) sử dụng thuật toán cộng tay từ phải sang trái. Mỗi lần thực hiện phép cộng, toàn bộ quá trình tính toán được ghi chi tiết vào file `history.log`.

## Cấu trúc dự án

```
MyBigNumber/
├── src/
│   ├── MyBigNumber.h        # Header - khai báo class
│   └── MyBigNumber.cpp      # Hiện thực thuật toán + logging
├── main.cpp                  # Unit test
├── README.md
└── .gitignore
```

## Yêu cầu

- Trình biên dịch C++ hỗ trợ C++11 trở lên (g++, clang++)

## Biên dịch

```bash
g++ -std=c++11 -o test main.cpp src/MyBigNumber.cpp
```

## Chạy test

```bash
./test
```

Sau khi chạy, kiểm tra file `history.log` để xem chi tiết từng bước tính toán:

```bash
cat history.log
```

## Ví dụ log

Khi thực hiện `sum("1234", "897")`, file `history.log` sẽ ghi:

```
=== Phep toan: 1234 + 897 ===
Buoc 1: Lay 4 cong voi 7 duoc 11. Luu 1 vao ket qua (Ket qua tam thoi: "1"). Ghi nho 1.
Buoc 2: Lay 3 cong voi 9 duoc 12. Cong tiep voi nho 1 duoc 13. Luu 3 vao ket qua (Ket qua tam thoi: "31"). Ghi nho 1.
...
Ket qua cuoi cung: 2131
---------------------------------------------------
```

## Tích hợp

Để sử dụng trong dự án khác, chỉ cần copy thư mục `src/` và include header:

```cpp
#include "src/MyBigNumber.h"

MyBigNumber bn;
std::string result = bn.sum("99999", "1"); // "100000"
```

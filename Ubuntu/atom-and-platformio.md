# Sử dụng Atom và PlatformIO làm công cụ lập trình cho các dự án IoT trên hệ điều hành Ubuntu 16.04

* **Thực hiện:** Thi Minh Nhựt - **Email:** thiminhnhut@gmail.com

* **Thời gian:** Ngày 02 tháng 09 năm 2017

## Nguồn tham khảo

* [PlatformIO IDE for Atom](http://docs.platformio.org/en/latest/ide/atom.html#ide-atomPlatformIO)

## Nội dung
### Cài đặt PlatformIO trên Atom
Phần này trình bày với cách sử dụng `PlatformIO` trên `Atom` với ngôn ngữ lập trình `C/C++` cho các board `Arduino` và `ESP`.

1. PlatformIO sử dụng [clang](http://clang.llvm.org/) để có thể tự động hoàn thành code `C/C++` thông minh.

    * Kiểm tra xem đã cài đặt `clang` trên máy tính hay chưa:

    ```bash
    $ clang --version
    ```

    * Cài đặt `clang` trên hệ điều hành Ubuntu:
    ```bash
    $ sudo apt-get install clang
    ```

    * Nếu không tự động hoàn thành mã được thì vào: `Menu: PlatformIO > Rebuild C/C++ Project Index (Autocomplete, Linter)` để rebuild lại.

1. Cài đặt `atom` theo hướng dẫn sau: [setup-atom.md](https://github.com/thiminhnhut/Atom/blob/master/Ubuntu/setup-atom.md)

1. Mở `atom` nhấn `Ctrl + ,` rồi chọn `Install`.

1. Tìm kiếm package `platformio-ide` để cài đặt.

### Sử dụng PlatformIO trên Atom

Mở chương trình Atom lên và thấy xuất hiện `PlatformIO` trên thanh menu là cài đặt thành công.

#### Tạo project với PlatformIO trên Atom như sau:

1. Tạo project với PlatformIO:

    ```bash
    Menu: PlatformIO > Initialize new Project or update existing
    ```

    * Chọn board và chọn nơi lưu project.

    * Nhấn vào nút `Process` để tạo project.

    * Cấu trúc của cây thư mục nằm trong project:

        + Thư mục `lib`: chứa các thư viện liên quan cho project.

        + Thư mục `src`: chứa file mã nguồn chính `main.cpp` (có thể thêm các file hỗ trợ (file `.h` hoặc `.cpp`) cho file mã nguồn `main.cpp`).

        + File `platformio.ini` là file cấu hình liên quan đến `project` (chúng ta sẽ tìm hiểu cách tùy chỉnh file này sau).

        + Thư mục `.pioenvs` chứa file mã nguồn sau khi biên dịch chương trình (file `main.cpp` và các thư viện nằm trong thư mục `lib`) để upload xuống vi điều khiển.

        + Thư mục `.piolibdeps` chứa các mã nguồn khi biên dịch các thư viện liên quan nhưng không nằm trong thư mục `lib`.

1. Tạo file `main.cpp` trong thư mục `src`. Chúng ta sẽ viết chương trình trong file `main.cpp`.

1. Trong thư mục `lib` là nơi chúng ta đặt các thư viện liên vào đây.

1. `Build` chương trình: chọn `Menu: PlatformIO > Build`. Nếu không xuất hiện lỗi nghĩa là build chương trình thành công.

1. `Upload` chương trình: `Menu: PlatformIO > Upload`.

1. Nếu trong quá trình `Build` chương trình vẫn còn xảy ra lỗi (trong khi chúng ta không tìm được nguyên nhân) thì chọn `Menu: PlatformIO > Clean` rồi chọn `Menu: PlatformIO > Build` để build lại.

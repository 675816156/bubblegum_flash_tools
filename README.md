# bubblegum_flash_tools

# Testing On Ubuntu

```bash
jun@jun:~/bubblegum/tools$ uname -a
Linux jun 4.2.0-16-generic #19-Ubuntu SMP Thu Oct 8 15:35:06 UTC 2015 x86_64 x86_64 x86_64 GNU/Linux
```

# How to build dfu tool
```bash
 cd dfu/ && make
```

# How to Run dfu tool
```bash
jun@jun:~/bubblegum/tools/dfu$ ./dfu
Usage: ./dfu board_name address [filename] [need_run]
     board_name: board's name, bubblegum etc.
     address: operation address, upload to or run to.
     filename: the file will be upload to 'address'. Optional.
     need_run: if run to 'address' after uploading, 1 yes, 0 no. Optional.

     NOTE:
     if no filename or need_run = 1, run to 'address'
     or, just upload 'filename' to 'address'
```

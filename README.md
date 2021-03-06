# pydasm

I had some trouble compiling **pydasm** on recent Windows platforms. This "slightly" modified version should works on
Windows 7/8/10 (Only tested on Windows 10).

## What is pydasm ?

**pydasm** is a python wrapper for [libdasm](https://github.com/axcheron/libdasm). It attempts to capture all the functionality of libdasm and bring its versatility to Python.

## Installation

for python2

1. install [Microsoft Visual C++ Compiler for Python 2.7](https://www.microsoft.com/en-us/download/details.aspx?id=44266)
2. 
```bash
git clone https://github.com/Cossack9989/pydasm
python setup.py install
```

for python3

the same above except python3-dev

## Usage

```python
import pydasm

buffer = '\x90\x31\xc9\x31\xca\x31\xcb'

offset = 0
while offset < len(buffer):
   i = pydasm.get_instruction(buffer[offset:], pydasm.MODE_32)
   print pydasm.get_instruction_string(i, pydasm.FORMAT_INTEL, 0)
   if not i:
     break
   offset += i.length
```

## Credits

origin author axcheron:
`Thanks to jt, skape, thief, spoonm and fine folks @nologin responsible for libdasm !
Special thanks to ero for creating and contributing pydasm.`
current updater C0ss4ck:
`if any question or exception ocurred, please contact me through c0ss4ck9989@gmail.com`

## License

This project is released under the BSD license. See LICENCE.
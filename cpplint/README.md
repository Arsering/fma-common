## Code Style
### Automatic cpplint check
Execute script `cpplint/git-hooks-init.sh` to configure your local git hooks
When run `git push`, the hook script is automatically triggered to check the cpp source files of this push with cpplint.
### Manual cpplint check
Before `git push`, use `cpplint` to check the c++ source files involved in this commit.
`cpplint` is just a python file that has been placed in the code repository, which path is `./cpplint/cpplint.py`.
For example, if you modify the two files `src/algo/algo.cpp` and `src/algo/algo.h`, execute the following command
```
./cpplint/cpplint.py src/algo/algo.cpp src/algo/algo.h
```
If `cpplint.py` reports some warnings, follow the prompts to modify until it is passed
You can also use the `./cpplint/check_code_style.sh` file, this script will check the source files involved in the latest git commit

If want to check all the cpp files in the `src` directory, use the following command
```
./cpplint/cpplint.py --recursive src
```
For more details, see [cpplint](https://github.com/cpplint/cpplint) or `./cpplint/cpplint.py --help`
### clang-format
You can use clang-format to format the code, the command is as follows:
```
clang-format -i src/algo/algo.cpp
```
clang-format tool needs to be installed on your own computer by yourself.
clang-format will look for the default configuration file `.clang-format` from the current path, which has been placed in the code repository and describes Google's cpp style.
For more Google's cpp style details, see [English Version](https://google.github.io/styleguide/cppguide.html#Forward_Declarations) or [中文版](https://google-styleguide.readthedocs.io/zh_CN/latest/google-cpp-styleguide/contents.html)

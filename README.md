<p align="center">
    <img src="https://user-images.githubusercontent.com/18141491/213256480-c8577c94-f0a9-41cb-8b57-420ce831949d.png">
</p>

<p align="center">
    <img src="https://img.shields.io/badge/Status-Completed-brightgreen.svg" alt="Status">
</p>

## Get_next_line

get_next_line is a 42 school project whose goal is to create a function that reads a line ending with a newline character from a file descriptor.

## How to use

- Clone the repository with `git clone`
- Compile your program with `get_next_line.c` and `get_next_line_utils.c`
- Include the header file `get_next_line.h` in your project

## Mandatory part

- [x] The function must be named `get_next_line`.
- [x] The function must be prototyped as follows: `int get_next_line(int fd, char **line);`
- [x] The function must return its result without ’\n’.
- [x] The function must return 1 when it reads a line, 0 when it has finished reading and -1 when an error has occurred.
- [x] The function must be able to handle memory leaks.

## Bonus part

- [x] Manage multiple file descriptors without losing the reading thread on each of the descriptors.

## Example

```bash
cc name_file.c get_next_line.c get_next_line_utils.c -o name_program #the name_program executable
```

```c
#include "get_next_line.h"

int main(void)
{
    int fd;
    char *line;

    fd = open("file.txt", O_RDONLY);
    while (get_next_line(fd, &line) > 0)
    {
        printf("%s\n", line);
        free(line);
    }
    close(fd);
    return (0);
}
```

## To do

- [ ] Better error handling
- [ ] Better Code

<a id="top"></a>

# get_next_line
`get_next_line` is a function that reads a line from a file descriptor. It allows reading a line ending with a newline character ('\n') from a file descriptor, one line at a time, without losing the reading thread.

## Table of Contents
- [About](#about)
- [Installation](#installation)
- [Usage](#usage)


## About
Mastering the project required grasping the functionality of the function within a program and acquainting oneself with static variables.

Additionally, the project emphasized the significance of addressing memory leaks. It is imperative for `get_next_line` and all subsequent projects to ensure the absence of any memory leaks.

## Installation
1. Clone this repository to your local machine:
	```sh
	git clone https://github.com/KarlQuerel/42-get_next_line.git
	```

2. Navigate to the project directory:
	```sh
	cd 42-get_next_line
	```
3. Include the `get_next_line.h` header file in your C source files.


## Usage
Once you have linked the `get_next_line` library to your project, you can call the function `get_next_line(int fd, char **line)` to read a line from the file descriptor `fd`.
```c
char	*get_next_line(int fd);
```
- The function returns 1 when a line has been read, 0 when the reading is complete, and -1 in case of error.

- The line read from the file descriptor will be stored in the variable pointed to by `line`.

Here is an example of how to use the functions:

```c
#include "get_next_line.h"

int main(void)
{
	int fd;
	char *line;

	fd = open("example.txt", O_RDONLY);
	while (get_next_line(fd, &line) > 0)
	{
		printf("%s\n", line);
		free(line);
	}
	close(fd);
	return (0);
}
```

For more information, refer to the [subject PDF](https://github.com/KarlQuerel/42-get_next_line/blob/master/docs/en.subject.pdf).

[Back to Top](#top)

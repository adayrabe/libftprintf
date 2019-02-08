# libftprintf

This is a general library that I will youse for the future projects. It contains libft library and printf function with following conversions:

1) diouxX with the following flags: hh, h, l and ll.

2) csp with flag l

3) flags #0-+ and space

4) minimum-field width

5) precision

6) b (for binary)

7) f with flags l and L

# libft
This project contains all the usefull functions i will be using in the future. The only functions here are write, malloc, free, exit and read.
There is also function fstat in ft_read_from_fd function to get the size of file and therefore to read faster.
Note: in future i will use libftprintf library, where will be all these functions + my realization of printf function. Available flags will be described in libftprintf project.

The files are in the following folders:
1)ft_lst (functions, used for list
2)ft_mem (functions for manipulating with memory
3)ft_put (functions to write something to the console)
4)ft_str (functions for manipulating with string)
5)ft_helpers (all the other funtcions)


# I) ft_lst

Works with the following list:
typedef struct        s_list
{
void            *content;
size_t            content_size;
struct s_list    *next;
}                    t_list;

1) int    ft_lst_size(t_list *head);

receives a pointer to head of list 
returns the size of list

2) void    ft_lstadd(t_list **alst, t_list *new);

receives a pointer to pointer to list and a pointer to a new element that has to be added
adds the element to the top of the list
returns nothing

3) void    ft_lstadd_back(t_list **head, t_list *elem);

receives a pointer to pointer to list and a pointer to a new element that has to be added
adds the element to the back of the list
returns nothing

4) void    ft_lstdel(t_list **alst, void (*del)(void *, size_t));

receives  pointer to pointer to list and a function with which to delete
deletes all the elements of the list
returns nothing

5) void    ft_lstdelone(t_list **alst, void (*del)(void *, size_t));

receives a pointer to poiner to list and a pointer to function
deletes this element of list with the given function
returns nothing

6) void    ft_lstiter(t_list *lst, void (*f)(t_list *elem));

receives a pointer to head of the list and a pointer to function
iterates through all the elements of the list, applying given function to each element
returns nothing

7) t_list    *ft_lstmap(t_list *lst, t_list *(*f)(t_list *elem));

recevies a pointer to list and a pointer to function
creates a new list by applying given function to each element of the list
returns the pointer to the head of newly created list

8) t_list    *ft_lstnew(void const *content, size_t content_size);

receives a content and size
creates a new element of list with given sontent and size
return a pointer to newly created element

# II) ft_mem

In this section, some functions work exactly as their library functions (without ft_ prefix). For the others, I will write an explanation.

1)  void    *ft_memalloc(size_t size)

Allocates (with malloc(3)) and returns a “fresh” memory area. The memory allocated is initialized to 0. If the alloca- tion fails, the function returns NULL.

2) void    *ft_memccpy(void *dst, const void *src, int c, size_t n);
3)  void    *ft_memchr(const void *s, int c, size_t n);
4) int    ft_memcmp(const void *s1, const void *s2, size_t n);
5) void    *ft_memcpy(void *dst, const void *src, size_t n);
6) void    ft_memdel(void **ap)

Takes as a parameter the address of a memory area that needs to be freed with free(3), then puts the pointer to NULL.

7) void    *ft_memmove(void *dst, const void *src, size_t len);
8) void    *ft_memset(void *b, int c, size_t len);

# III) ft_put

1) void    ft_putchar(char c)
Outputs the character c to the standard output.

2) void    ft_putchar_fd(char c, int fd);
Outputs the char c to the file descriptor fd.

3)  void    ft_putendl(char const *s);
Outputs the string s to the standard output followed by a ’\n’.

4) void    ft_putendl_fd(char const *s, int fd);
Outputs the string s to the file descriptor fd followed by a ’\n’.

5) void    ft_putnbr(int n);
Outputs the integer n to the standard output.

6) void    ft_putnbr_fd(int n, int fd);
Outputs the integer n to the file descriptor fd.

7) void    ft_putstr(char const *s);
Outputs the string s to the standard output.

8) void    ft_putstr_fd(char const *s, int fd);
Outputs the string s to the file descriptor fd.

# IV) ft_str

In this section, as in section II some functions work exactly as their library functions (without ft_ prefix). For the others, I will write an explanation.

1)  char    *ft_str_to_upper(char *word);

Receives a string, makes all letters in it as uppercase and returns this string

2) char    *ft_str_tolower(char *word);

Receives a string, makes all letters in it as lowercase and returns this string

3) void    ft_str_unsigned_concat(unsigned char **s1, unsigned char *s2, size_t l1, size_t l2);

Receives a pointer to unsigned string, another unsigned string and their lengths. Concatenates first string with a second and writes it to the first string. Returns nothing

4) void    ft_str_unsigned_del(unsigned char **s);

Deletes an unsigned string

5) unsigned char    *ft_str_unsigned_new(size_t len);

Creates a new unsigned string with the given length

6) char    *ft_strcat(char *s1, const char *s2);
7) char    *ft_strchr(const char *s, int c);
8) void    ft_strclr(char *s)

Sets every character of the string to the value ’\0’.

9) int    ft_strcmp(const char *s1, const char *s2);
10) void    ft_strconcat(char **s1, char *s2, size_t l1, size_t l2);

Receives a pointer to  string, another string and their lengths. Concatenates first string with a second and writes it to the first string. Returns nothing

11) char    *ft_strcpy(char *dst, const char *src);
12) void    ft_strdel(char **as);

Takes as a parameter the address of a string that need to be freed with free(3), then sets its pointer to NULL.

13) char    *ft_strdup(const char *s1);

Qorks as strdup, but if s1 == NULL, it doesn;t segfault, it returns NULL

14) char    *ft_strdup_until(char *line, char c);

Creates a new string from the given string until character c or until the end of first string

15) int    ft_strequ(const char *s1, const char *s2);

Lexicographical comparison between s1 and s2. If the 2 strings are identical the function returns 1, or 0 otherwise.

16) void    ft_striter(char *s, void (*f)(char *));

Applies the function f to each character of the string passed as argument. Each character is passed by address to f to be modified if necessary.

17) void    ft_striteri(char *s, void (*f)(unsigned int, char *));

Applies the function f to each character of the string passed as argument, and passing its index as first argument. Each character is passed by address to f to be modified if necessary.

18) char    *ft_strjoin(char const *s1, char const *s2);

Allocates (with malloc(3)) and returns a “fresh” string end- ing with ’\0’, result of the concatenation of s1 and s2. If the allocation fails the function returns NULL.

19) size_t    ft_strlcat(char *dst, const char *src, size_t size);
20) unsigned long    ft_strlen(const char *src);
21) char    *ft_strmap(const char *s, char (*f)(char));

Applies the function f to each character of the string given as argument to create a “fresh” new string (with malloc(3)) resulting from the successive applications of f.

22) char    *ft_strmapi(const char *s, char (*f)(unsigned int, char));

Applies the function f to each character of the string passed as argument by giving its index as first argument to create a “fresh” new string (with malloc(3)) resulting from the suc- cessive applications of f.

23) char    *ft_strncat(char *s1, const char *s2, size_t n);
24) int    ft_strncmp(char *s1, char *s2, size_t n);
25) char    *ft_strncpy(char *dst, const char *src, size_t len);
26) int    ft_strnequ(const char *s1, const char *s2, size_t n)

Lexicographical comparison between s1 and s2 up to n char- acters or until a ’\0’ is reached. If the 2 strings are identical, the function returns 1, or 0 otherwise.

27) char    *ft_strnew(size_t size);

Allocates (with malloc(3)) and returns a “fresh” string end- ing with ’\0’. Each character of the string is initialized at ’\0’. If the allocation fails the function returns NULL.

28) char    *ft_strnstr(const char *big, const char *little, size_t len);
29) char    *ft_strrchr(const char *s, int c);
30) char        **ft_strsplit(char const *s, char c);

Allocates (with malloc(3)) and returns an array of “fresh” strings (all ending with ’\0’, including the array itself) ob- tained by spliting s using the character c as a delimiter. If the allocation fails the function returns NULL. Example : ft_strsplit("*hello*fellow***students*", ’*’) re- turns the array ["hello", "fellow", "students"].

31) char    *ft_strstr(char *str, char *to_find);
32) char    *ft_strsub(const char *s, unsigned int start, size_t len);

Allocates (with malloc(3)) and returns a “fresh” substring from the string given as argument. The substring begins at indexstart and is of size len. If start and len aren’t refer- ing to a valid substring, the behavior is undefined. If the allocation fails, the function returns NULL.

33) char        *ft_strtrim(char const *s);

Allocates (with malloc(3)) and returns a copy of the string given as argument without whitespaces at the beginning or at the end of the string. Will be considered as whitespaces the following characters ’ ’, ’\n’ and ’\t’. If s has no whites- paces at the beginning or at the end, the function returns a copy of s. If the allocation fails the function returns NULL.


# V) ft_helpers

In this section, as in section II and IV some functions work exactly as their library functions (without ft_ prefix). For the others, I will write an explanation.

1) int                ft_atoi(char *str);
2) void    ft_bzero(void *s, size_t n);
3) int    ft_isalnum(int c);
4) int    ft_isalpha(int c);
5) int    ft_isascii(int c);
6) int    ft_isdigit(int c);
7) int    ft_isprint(int c);
8) char    *ft_itoa(int n);

Allocate (with malloc(3)) and returns a “fresh” string end- ing with ’\0’ representing the integer n given as argument. Negative numbers must be supported. If the allocation fails, the function returns NULL.

9) int    ft_max_in_array(int *arr, size_t size);

Returns a maximum value in an array of integers

10) unsigned long    ft_pow(size_t x, int pow);

Returns a power of number. Doesnt work with powers under 0

11) size_t    read_from_fd(int fd, unsigned char **line);

Rescieves a file descriptor (that should be valid) and a pointer to unsigned  string. Reads all the file right away, using fstat function from sys/stat.h library and writes it to given string. Returns the amunt of bytes read.

12) int    *ft_sort_int(int *arr, size_t size);

Sorts an integer array using bubble sort. Will add other sorting algorithms in the future

13) int    ft_sqrt(int a);

returns -1 if given number is less then 0
Otherwise, return the biggest possible number that can be swuared and that would be less than or equal to given number. For example, sqrt(16) = 14, sqrt(26) = 5, sqrt(35) = 5

14) int    ft_tolower(int c);
15) int    ft_toupper(int c);
16) int                get_next_line(const int fd, char **line);

Rescieves a file descriptor and a pointer to  string. In case of an error, returns -1. The function reads from the file descriptor until it meets newline character or end of file and writes the contnent to the given string. Returns 1 in case of success and 0 if it meets the end of file.

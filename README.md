# Fix My Code Challenge

Bug-fixing exercises across Python, JavaScript, Ruby, and C. Each script contains an intentional bug to identify and correct.

## Challenges

| # | File | Language | Bug to fix |
|---|------|----------|------------|
| 0 |  | Python | Condition order — FizzBuzz case never triggered |
| 1 |  | JavaScript | Square prints incorrectly |
| 2 |  | Ruby | Sort logic broken |
| 3 |  | Python | User model — attribute issue |
| 4 |  | C | Doubly linked list — node deletion at index |

## Run

```bash
# Python
python3 challenge/0-fizzbuzz.py 89

# JavaScript
node challenge/1-print_square.js 4

# Ruby
ruby challenge/2-sort.rb

# C
cd challenge/4-delete_dnodeint
gcc *.c -o delete_test && ./delete_test
```

## Structure

```
challenge/
├── 0-fizzbuzz.py
├── 1-print_square.js
├── 2-sort.rb
├── 3-user.py
└── 4-delete_dnodeint/
    ├── main.c
    ├── delete_dnodeint_at_index.c
    ├── add_dnodeint_end.c
    ├── free_dlistint.c
    ├── print_dlistint.c
    └── lists.h
```

---

Holberton School France

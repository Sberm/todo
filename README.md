## todo

A todo file format and a summary script. Check out `todo.txt`, `todo2.txt`, `todo-exp1.txt`, `todo-exp2.txt` for examples.

### Installation

```sh
./install.sh
```

requirement: have python3 installed

### Usage

run `pending -h` for command line options

### Examples:

```todo
$ cat todo-exp1.txt
this is a todo item
[OK]this is a completed todo item
[OK]also an item, but it spans multiple lines, \
    so it can store more information

# this is a comment that `pending` will ignore

2024-11-09
# dates like '2024-12-01' suit as a separator for todo items. `pending` with no option will only collect the items of today
drink milk
eat cheese burgers

$ cat todo-exp2.txt
# from the start to the first specified date will be viewed as today,
and will always be shown when running pending.

this is a global todo item that will always be shown
[OK]this is a completed global todo item

2024-11-18
Don't laugh at mom's jokes
Go to the court, remember to take the pen
# this is a multi-line todo item
Tell Uncle Jerome to bring the coffee cup so that no harm will come to the poor \
insects from South America, which I bought for 700 dollars per gram, along with \
their colony made from their saliva.
```

Use with `watch` for continuous updates
```bash
watch -n 0.5 -d --color ./pending
```

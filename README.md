## todo

A todo file format and a summary script. Check out `todo.txt` and `todo2.txt` for examples.

grammar:

```todo
# this is a comment that `pending` will ignore

# dates suit as a separator for todo items. `pending` with no option will only
# collect the pending and finished todo items of today

# from the start to the first specified date will be viewed as today, and will
always be shown when running pending.

this is a global todo item that will always be shown

# This is a date and serves as a separator for TODO items. When running
# `pending`, this will be prepended to a TODO item.
2024-11-09
drink milk
eat cheese burgers

2024-11-18
Don't laugh at mom's jokes
Go to the court, remember to take the pen
# this is a multi-line todo item
Tell Uncle Jerome to bring the coffee cup so that no harm will come to the poor \
insects from South America, which I bought for 700 dollars per gram, along with \
their colony made from their saliva.
```

```bash
todo $ cat todo.txt
# from the start to the first specified date will be viewed as today
read Shakespeare
write an essay
[OK]drink water

# This is a comment. This comment as well as empty lines are ignored.
go shopping

eat food
  # You better eat some food, this will make you feel so much better.
  # Such as grapes, mangoes, and apples

2024-11-18
[OK]read a book
install the curtains

2024-11-6
[OK]pay rent
buy a new pair of shoes
drink hot water
todo $ ./pending

  2024-12-03 read Shakespeare
  2024-12-03 write an essay
  2024-12-03 go shopping
  2024-12-03 eat food

  2024-12-03 [OK]drink water

todo $ ./pending -a

  2024-12-03 read Shakespeare
  2024-12-03 write an essay
  2024-12-03 go shopping
  2024-12-03 eat food
  2024-11-18 install the curtains
  2024-11-06 buy a new pair of shoes
  2024-11-06 drink hot water

  2024-12-03 [OK]drink water
  2024-11-18 [OK]read a book
  2024-11-06 [OK]pay rent

todo $ ./pending -p

  2024-12-03 read Shakespeare
  2024-12-03 write an essay
  2024-12-03 go shopping
  2024-12-03 eat food
  2024-11-18 install the curtains
  2024-11-06 buy a new pair of shoes
  2024-11-06 drink hot water

todo $ ./pending -h
usage: pending [-h] [-a] [-i file] [-p] [-v]

optional arguments:
  -h, --help            show this help message and exit
  -a, --all             print all tasks
  -i file, --input file
                        default: todo.txt, path to the todo file
  -p, --pending         only show pending tasks
  -v, --version         print current version
```

Use with `watch` for continuous updates
```bash
watch -n 0.5 -d --color ./pending
```

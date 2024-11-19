## todo

A todo file format and a summary script

```bash
# an example of a todo file
$ cat todo.txt
2024-11-18
eat food
read Shakespeare
write an essay
[OK]drink water

2024-11-6
[OK]pay rent
buy a new pair of shoes
drink hot water

$ ./pending

  2024-11-18 eat food
  2024-11-18 read Shakespeare
  2024-11-18 write an essay

  2024-11-18 [OK]drink water

$ ./pending -a

  2024-11-18 eat food
  2024-11-18 read Shakespeare
  2024-11-18 write an essay
  2024-11-06 buy a new pair of shoes
  2024-11-06 drink hot water

  2024-11-18 [OK]drink water
  2024-11-06 [OK]pay rent

$ ./pending -h
usage: pending [-h] [-a] [-i file]

optional arguments:
  -h, --help            show this help message and exit
  -a, --all             print all todo items
  -i file, --input file
                        default: todo.txt, path to the todo file
```

Use with `watch` for continuous updates
```bash
watch -n 0.5 -d --color ./pending
```

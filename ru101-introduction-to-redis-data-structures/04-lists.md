## Chapter: Lists Explained

Some operations related to lists in Redis.

### Using `RPUSH`

The `RPUSH` command is used to push one or multiple values to the right end of a Redis list.

```bash
RPUSH playlist 1 2 3 4 5 6 7 8 9 10
```

### Using `LPOP`

The `LPOP` command removes and returns the leftmost element from a Redis list.

```bash
LPOP playlist
```

### Using `RPOP`

The `RPOP` command removes and returns the rightmost element from a Redis list.

```bash
RPOP playlist
```

### Using `LRANGE`

The `LRANGE` command retrieves elements from a Redis list within a specified range.

```bash
LRANGE playlist 0 5
```

### Using `LLEN`

The `LLEN` command returns the length (number of elements) of a Redis list.

```bash
LLEN playlist
```

### Using `LPUSH`

The `LPUSH` command is used to push one or multiple values to the left end of a Redis list.

```bash
LPUSH playlist 99 98 97 96 95
```

### Using `LSET`

The `LSET` command is used to set the value of an element at a specific index in a Redis list.

```bash
LSET playlist 0 100
```

Link of documentation: https://redis.io/commands/?group=list

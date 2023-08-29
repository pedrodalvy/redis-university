## Chapter: Strings Explained

Some operations related to strings in Redis.

### Using `INCR`

The `INCR` command increments the integer value of a key by 1.

```bash
INCR user:23:visit-count
# returns 1
GET user:23:visit-count

INCR user:23:visit-count
# returns 2
GET user:23:visit-count
```

> Note: The key does not need to exist for INCR to work.

### Using `INCRBY`
The `INCRBY` command increments the integer value of a key by a specified amount.

```bash
# will set value to 30
INCRBY user:66:credit-balance 30

# will set value to 60
INCRBY user:66:credit-balance 30
```

> Note: Works with negative numbers
> ```bash
>  # will set value to -100
>  INCRBY user:11:credit-balance -100
> ```

### Using `DECR`
The `DECR` command decrements the integer value of a key by 1.

```bash
# sets value to -1
DECR user:14:visit-count

# sets value to -2
DECR user:14:visit-count
```

### Using `DECRBY`
The `DECRBY` command decrements the integer value of a key by a specified amount.

```bash
# sets value to -30
DECRBY user:43:credit-balance 30

# sets value to -60
DECRBY user:43:credit-balance 30
```

### Using `INCRBYFLOAT`
The `INCRBYFLOAT` command increments the value of a key by a floating-point number.

```bash
# sets value to 0.5
INCRBYFLOAT user:99:credit-balance 0.5

# sets value to 1
INCRBYFLOAT user:99:credit-balance 0.5
```

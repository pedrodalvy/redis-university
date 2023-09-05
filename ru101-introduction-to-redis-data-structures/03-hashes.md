## Chapter: Hashes Explained

Some operations related to hashes in Redis.

### Using `HSET`

The `HSET` command is used to set multiple field-value pairs within a Redis hash.

```bash
HSET player:42 name Artexius race Elf level 4 hp 20 gold 20
```

### Using `HGETALL`

The `HGETALL` command retrieves all field-value pairs from a Redis hash.

```bash
HGETALL player:42
```

### Using `HGET`

The `HGET` command retrieves the value of a specific field within a Redis hash.

```bash
HGET player:42 name
```

### Using `HSET` to Update a Field

You can use `HSET` to update a field within a Redis hash.

```bash
HSET player:42 status dazed
```

### Using `HDEL` to Delete a Field

The `HDEL` command is used to delete a specific field from a Redis hash.

```bash
HDEL player:42 status
```

### Using `HINCRBY`

The `HINCRBY` command increments the integer value of a field within a Redis hash by a specified amount.

```bash
HINCRBY player:42 gold 120
```

### Using `HEXISTS`

The `HEXISTS` command checks if a specific field exists within a Redis hash.

```bash
HEXISTS player:42 status
```


### Using `HSCAN` to Match Fields

The `HSCAN` command with the `MATCH` option is used to scan fields within a Redis hash that match a specified pattern.

```bash
HSET product:34 name "Rubber Duck" price 1.99 category "Toys" size:height 3 size:width 4 size:length 5
HSCAN product:34 0 MATCH size:*
```

Link of documentation: https://redis.io/commands/?group=hash

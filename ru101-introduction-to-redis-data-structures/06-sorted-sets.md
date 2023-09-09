## Chapter: Sorted Sets Explained

Some operations related to sorted sets in Redis.

### Using `ZADD`

The `ZADD` command is used to add members to a Redis sorted set along with their scores.

```bash
ZADD page:visitors 10 home
ZADD page:visitors 5 about 3 faq
```

### Using `ZRANGE`

The `ZRANGE` command retrieves members from a Redis sorted set within a specified range, sorted by their scores.

```bash
# returns "faq" and "about" (lowest scores)
ZRANGE page:visitors 0 1

# returns "faq" (3), "about" (5) with scores
ZRANGE page:visitors 0 1 WITHSCORES
```

### Using `ZREVRANGE`

The `ZREVRANGE` command retrieves members from a Redis sorted set in reverse order within a specified range, sorted by their scores.

```bash
# returns "home" (10) and "about" (5) with scores
ZREVRANGE page:visitors 0 1 WITHSCORES

# returns all members and scores sorted by the highest scores
ZREVRANGE page:visitors 0 -1 WITHSCORES
```

### Using `ZRANK` and `ZREVRANK`

The `ZRANK` command returns the rank of a member in a Redis sorted set, with the lowest score having rank 0. The `ZREVRANK` command returns the rank in reverse order.

```bash
# returns 2 (rank of "home" with a score of 10)
ZRANK page:visitors home

# returns 0 (rank of "home" in reverse order)
ZREVRANK page:visitors home
```

### Using `ZSCORE`

The `ZSCORE` command retrieves the score associated with a member in a Redis sorted set.

```bash
# returns 10 (score of "home")
ZSCORE page:visitors home
```

### Using `ZCOUNT`

The `ZCOUNT` command counts the number of members in a Redis sorted set with scores within a specified range.

```bash
# returns 2 (members with scores between 0 and 5)
ZCOUNT page:visitors 0 5

# returns 3 (members with scores between 0 and 10)
ZCOUNT page:visitors 0 10
```

### Using `ZINCRBY`

The `ZINCRBY` command increments the score of a member in a Redis sorted set by a specified amount.

```bash
# increment 1 visitor to the "home" page
ZINCRBY page:visitors 1 home
```

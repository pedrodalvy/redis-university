## Chapter: Sets Explained

Some operations related to sets in Redis.

### Using `SADD`

The `SADD` command is used to add one or more members to a Redis set.

```bash
# returns 2
SADD players:online 42 43
# returns 0 because 43 is already in the set
SADD players:online 43
```

### Using `SMEMBERS`

The `SMEMBERS` command retrieves all members of a Redis set.

```bash
# returns 42 and 43
SMEMBERS players:online
```

### Using `SREM`

The `SREM` command removes one or more members from a Redis set.

```bash
SREM players:online 43
```

### Using `SCARD`

The `SCARD` command returns the number of members in a Redis set.

```bash
SCARD players:online
```

### Using `SISMEMBER`

The `SISMEMBER` command checks if a member exists in a Redis set.

```bash
# returns 1
SISMEMBER players:online 42
# returns 0
SISMEMBER players:online 40
```

### Intersections, Differences, and Unions

We can perform set operations such as intersections, differences, and unions on Redis sets.

```bash
SADD page:home:visitors john smith anna
SADD page:about:visitors john peter

# returns "john" (common member)
SINTER page:home:visitors page:about:visitors

# returns "anna" and "smith" (members in the first set but not the second)
SDIFF page:home:visitors page:about:visitors

# returns "peter" (members in the second set but not the first)
SDIFF page:about:visitors page:home:visitors

# returns "john," "smith," "anna," and "peter" (all members in both sets)
SUNION page:home:visitors page:about:visitors
```

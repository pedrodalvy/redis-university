## Chapter: Working with Keys

Some operations related to keys in Redis.

### Creating Keys
To create a key, you can use the `SET` command.

```bash
# Create keys and associate values
SET registeredusers:1000:followers 1
SET registeredusers:1001:followers 10

# Case-sensitive keys
SET RegisteredUsers:1000:followers 2
```

> Note: Keys in Redis are case-sensitive.

### Retrieving Values by Key
To retrieve a value associated with a key, you can use the `GET` command.

```bash
GET registeredusers:1000:followers
GET RegisteredUsers:1000:followers
```

### Listing Keys by Pattern
To retrieve keys that match a specific pattern, you can use the `KEYS` command or the `SCAN` command for better performance.

```bash
# Using KEYS command
KEYS registeredusers*

# Using SCAN command with cursor and count
SCAN 0 MATCH registeredusers* COUNT 10
```

### Deleting Keys
To remove keys and their associated values, you can use the `UNLINK` or `DEL` command.

```bash
UNLINK registeredusers:1000:followers
DEL registeredusers:1000:followers
```

### Checking Key Existence
You can check if a key exists using the `EXISTS` command.

```bash
EXISTS registeredusers:1000:followers
EXISTS registeredusers:1001:followers
```

### Creating Keys Conditionally
The `SET` command can be used with modifiers to create keys conditionally. The `NX` option ensures the key is created only if it doesn't exist.

```bash
# Create if key doesn't exist
SET inventory:100-meters-womens-final 1000 NX

# Attempt to create again (will return nil)
SET inventory:100-meters-womens-final 2000 NX
```

### Updating Keys Conditionally
The `SET` command can also be used to update keys conditionally. The `XX` option ensures the key is updated only if it already exists.

```bash
# Update if key exists
SET inventory:100-meters-womens-final 1000 XX

# Attempt to update non-existent key (will return nil)
SET inventory:200-meters-womens-final 1000 XX
```

### Working with Key Time-to-Live (TTL)

Redis supports setting a Time-to-Live (TTL) for keys, allowing them to expire after a certain duration. This is useful for managing data with a limited lifespan.

### Set TTL for a Key

You can set a TTL for a key using the `SET` command along with the `EX` (seconds) or `PX` (milliseconds) options.

```bash
# Set TTL for a key in milliseconds (50 seconds)
SET seat-hold Row:A:Seat:4 PX 50000

# Set TTL for a key in seconds
SET seat-hold Row:A:Seat:4 EX 50
```

### Updating TTL for a Key
You can update the TTL for a key using the `EXPIRE` (seconds) or `PEXPIRE` (milliseconds) command.

```bash
# Update TTL to 1 second
EXPIRE seat-hold 1
PEXPIRE seat-hold 1000
```

### Inspecting TTL of a Key
To check the remaining time for a key's TTL, you can use the `TTL` command (in seconds) or the `PTTL` command (in milliseconds).

```bash
TTL seat-hold
PTTL seat-hold
```

### Retaining a Key

If you want to retain a key and prevent it from expiring, you can use the `PERSIST` command.

```bash
PERSIST seat-hold

# will return -1 (indicating no expiration)
TTL seat-hold
```

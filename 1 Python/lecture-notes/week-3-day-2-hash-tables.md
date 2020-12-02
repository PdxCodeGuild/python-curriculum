# Week 3, day 2

## Hash Tables

Today we talked about how dictionaries can be implemented under the hood using a hash table.

Key points:

* a hash function is used to map keys into indices in a fixed-size array
* hashing is O(1) (constant time)
* the value associated with a key can be looked up in constant time by hashing the key and then accessing the corresponding index in the hash table

### Example code

Note, the following code was part of an impromptu discussion about how dictionaries work under the hood. It shouldn't be considered a "robust" dictionary implementation.

```python
# simple dictionary example

def dictionary():
    length = 100
    array = [None]*length

    def add_or_lookup(key, value=None):
        if value != None:
            index = hash_fn(key, length)
            array[index] = value
        else:
            index = hash_fn(key, length)
            return array[index]

    return add_or_lookup


# create dictionary
# d = dictionary()

# insert key/value pair
# d('key', 'value')

# lookup value associated with key
# d('key') -> 'value'

def hash_fn(key, length):
    # we use python's builtin hash function
    # we need to convert to a positive integer, and then restrict the range to be within our list's length
    return abs(hash(key)) % length

```
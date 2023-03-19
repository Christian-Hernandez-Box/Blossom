# Blossom

The language of the flowers has a long history and has often been a topic resigned to the domain of dusty books in a thrift bookseller or a library. With Blossom, we want to give people lightning fast access to all of the possible meanings of their favorite flowers.

In this project, we are going to implement a hash map to relate the names of flowers to their meanings. In order to avoid collisions when our hashing function collides the names of two flowers, we are going to use separate chaining. We will implement the Linked List data structure for each of these separate chains.

```
class HashMap:
  def __init__(self, size):
    self.array_size = size
    self.array = [LinkedList() for array in range(size)]

  def hash(self, key):
    hash_code = sum(key.encode())
    return hash_code

  def compress(self, hash_code):
    return hash_code % self.array_size

  def assign(self, key, value):
    array_index = self.compress(self.hash(key))
    payload = Node([key, value])
    list_at_array = self.array[array_index]

    for item in list_at_array:
      if item[0] == key:
        item[1] == value
        return

    list_at_array.insert(payload)

  def retrieve(self, key):
    array_index = self.compress(self.hash(key))
    list_at_index = self.array[array_index]

    for item in list_at_index:
      if item[0] == key:
        return item[1]
      else:
        return None

blossom = HashMap(len(flower_definitions))

for element in flower_definitions:
  blossom.assign(element[0], element[1])

print(blossom.retrieve('daisy'))
```

Output Example:

```
Innocence
```

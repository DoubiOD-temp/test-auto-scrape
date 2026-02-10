# Master the Map: A Comprehensive Guide to JavaScript Map Methods

A **Map** is a collection of keyed data items, similar to an Object. However, the main difference is that Map allows keys of **any type** (including objects, functions, and primitives) and maintains the **insertion order** of elements.

---

## 1. Core Properties & Initialization

### Creating a Map

```javascript
const myMap = new Map();
// Or with initial data
const userMap = new Map([
  ["id", 1],
  ["name", "Adam"],
  ["role", "Admin"],
]);
```

### The `size` Property

Returns the number of key-value pairs in the Map.

```javascript
console.log(myMap.size); // 0
```

---

## 2. Essential Map Methods

### `set(key, value)`

Adds or updates an element with a specified key and value. It returns the Map object, allowing for method chaining.

```javascript
myMap
  .set("status", "online")
  .set("priority", 1)
  .set({ type: "internal" }, "Secret Code");
```

### `get(key)`

Retrieves the value associated with the key. Returns `undefined` if the key doesn't exist.

```javascript
const status = myMap.get("status"); // 'online'
```

### `has(key)`

Returns a boolean indicating whether an element with the specified key exists or not.

```javascript
if (myMap.has("priority")) {
  console.log("Priority is set!");
}
```

### `delete(key)`

Removes the specified element by key. Returns `true` if it existed and was removed, `false` otherwise.

```javascript
myMap.delete("status"); // true
```

### `clear()`

Removes all key-value pairs from the Map.

```javascript
myMap.clear();
console.log(myMap.size); // 0
```

---

## 3. Iteration Methods

Maps preserve the order of elements, giving you several ways to traverse them:

### `keys()`

Returns an iterator for the keys.

```javascript
for (let key of userMap.keys()) {
  console.log(key);
}
```

### `values()`

Returns an iterator for the values.

```javascript
for (let value of userMap.values()) {
  console.log(value);
}
```

### `entries()`

Returns an iterator for `[key, value]` pairs (the default iterator for Map).

```javascript
for (let [key, value] of userMap.entries()) {
  console.log(`${key}: ${value}`);
}
```

### `forEach(callback)`

Standard array-like iteration.

```javascript
userMap.forEach((value, key) => {
  console.log(`${key} is ${value}`);
});
```

---

## 4. Key Differences: Map vs. Object

| Feature         | Map                               | Object                     |
| :-------------- | :-------------------------------- | :------------------------- |
| **Key Types**   | Any (Object, Function, Primitive) | String or Symbol           |
| **Order**       | Preserves insertion order         | Generally not guaranteed   |
| **Size**        | Built-in `size` property          | Must calculate manually    |
| **Performance** | Better for frequent add/remove    | Standard for data modeling |
| **Iteration**   | Directly iterable                 | Requires `Object.keys()`   |

---

## 5. Frequency Patterns & Use Cases

- **Caching/Memoization**: Maps are excellent for storing results of expensive function calls keyed by complex objects.
- **Data Association**: Linking metadata to DOM elements or specific objects without polluting the objects themselves.
- **Large Collections**: More performant than objects for massive datasets with frequent modifications.

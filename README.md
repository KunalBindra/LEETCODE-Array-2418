# LEETCODE-Array-2418
Let's go through a dry run of the `sortPeople` method in the `Solution` class.

### Initial Setup
We have two arrays:
- `names`: An array of people's names.
- `heights`: An array of corresponding heights.

For example:
```java
String[] names = {"Alice", "Bob", "Charlie"};
int[] heights = {150, 180, 165};
```

### Step-by-Step Execution

1. **Initialization:**
   ```java
   List<Pair<Integer, String>> heightAndNames = new ArrayList<>();
   ```

2. **Populating the List:**
   ```java
   for (int i = 0; i < names.length; ++i)
     heightAndNames.add(new Pair<>(heights[i], names[i]));
   ```
   After this loop, `heightAndNames` will be:
   ```
   [(150, "Alice"), (180, "Bob"), (165, "Charlie")]
   ```

3. **Sorting:**
   ```java
   Collections.sort(heightAndNames, (a, b) -> b.getKey() - a.getKey());
   ```
   The list `heightAndNames` will be sorted in descending order of heights:
   ```
   [(180, "Bob"), (165, "Charlie"), (150, "Alice")]
   ```

4. **Reassigning Names:**
   ```java
   for (int i = 0; i < heightAndNames.size(); ++i)
     names[i] = heightAndNames.get(i).getValue();
   ```
   After this loop, the `names` array will be:
   ```
   ["Bob", "Charlie", "Alice"]
   ```

5. **Returning the Result:**
   ```java
   return names;
   ```
   The method returns:
   ```
   ["Bob", "Charlie", "Alice"]
   ```

### Complete Dry Run

Given the initial arrays:
```java
String[] names = {"Alice", "Bob", "Charlie"};
int[] heights = {150, 180, 165};
```
After running the `sortPeople` method, the resulting `names` array will be:
```java
["Bob", "Charlie", "Alice"]
```

This is the expected outcome as the names are sorted based on the corresponding heights in descending order.

# Tally An Array

Given an array:
```
arr = [1, 2, 3, 3, 5, 5, 5, 5]
```

To count the occurrences of each unque element (since ruby 2.7):

```
arr.tally
 => {1=>1, 2=>1, 3=>2, 5=>4}
```

My old way of doing this, and valid pre-2.7:

```
arr.group_by(&:itself).transform_values(&:size)
 => {1=>1, 2=>1, 3=>2, 5=>4}
```

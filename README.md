# C++ Performance

## Memory
- Sequential access faster than random
- Instructions should not have dependencies, e.g.

Slow:
````cpp
a += 1
b += a
c += b
d += c
````

Fast:
````cpp
a += 1
b += 1
c += 1
d += 1
````

## Vectors

If you know the size in advance, you can put things faster with direct index.

Slow:
````cpp
std::vector<double> numbers;
for (int i = 0; i < 100; i++) {
  numbers.push_back(10);
}
````

Fast:
````cpp
std::vector<double> numbers (100);
for (int i = 0; i < 100; i++) {
  numbers[i] = 10;
}
````

## Convert values first to your datatype, then do the calculations

````cpp
int dataSize = 10000;
float *floatData;
floatData = (float *)malloc(sizeof(float)*dataSize);
std::copy(data, data + dataSize, floatData);
````

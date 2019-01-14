# Data 3-6: Python - Grouping

We can use `for` loops, `if` statements, and `dicts` to group data.

```python
from pprint import pprint

cars = [
    {"model": "Yaris", "make": "Toyota"},
    {"model": "Auris", "make": "Toyota"},
    {"model": "Camry", "make": "Toyota"},
    {"model": "Prius", "make": "Toyota"},
    {"model": "Civic", "make": "Honda"},
    {"model": "Model 3", "make": "Tesla"},
]

cars_by_make = {}
for car in cars:
    make = car['make']
    if make in cars_by_make:
        cars_by_make[make].append(car)
    else:
        cars_by_make[make] = [car]

pprint(cars_by_make)

# {'Honda': [{'make': 'Honda', 'model': 'Civic'}],
#  'Tesla': [{'make': 'Tesla', 'model': 'Model 3'}],
#  'Toyota': [{'make': 'Toyota', 'model': 'Yaris'},
#             {'make': 'Toyota', 'model': 'Auris'},
#             {'make': 'Toyota', 'model': 'Camry'},
#             {'make': 'Toyota', 'model': 'Prius'}]}

number_of_cars_by_make = {}
for car in cars:
    make = car['make']
    if make in number_of_cars_by_make:
        number_of_cars_by_make[make] += 1
    else:
        number_of_cars_by_make[make] = 1

pprint(number_of_cars_by_make)

# {'Honda': 1, 'Tesla': 1, 'Toyota': 4}
```

### ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. Use excel to add a column `color` to `vegtables.csv`.
2. Read `vegtables.csv` into a variable called `vegtables`.
3. Group `vegtables` by `color` as a variable `vegtables_by_color`.
4. Output `vegtables_by_color` into a json called `vegtables_by_color.json`.
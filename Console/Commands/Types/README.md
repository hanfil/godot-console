
## Supported console types.

### Engine types:

[`TYPE_BOOL`](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/Bool.gd), [`TYPE_INT`](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/Int.gd), [`TYPE_REAL`](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/Float.gd) and [`TYPE_STRING`](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/String.gd).


### Custom types:

 - [**IntRange**](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/IntRange.gd) (*int* min_value = 0, *int* max_value = 100, *int* step = 1)

Difference between Int range and Float range is that in Int range values are rounded to integers.


- [**FloatRange**](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/FloatRange.gd) (*float* min_value = 0, *float* max_value = 100, *float* step = 0)


- [**Filter**](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/Filter.gd) (*Array* filterList, *int* mode = ALLOW)

Possible `mode`s are: `Filter.ALLOW` and `Filter.DENY`


### Adding your own types

To add custom type extend [`Console/Commands/Types/BaseType.gd`](https://github.com/QuentinCaffeino/godot-console/blob/master/Console/Commands/Types/BaseType.gd)


## Example

```gdscript
var health = 5

func _ready():
	Console.register('set_health', {
		'description': 'Set health',
		'args': [Console.FloatRange.new(0, 5, 0.5)],
		'target': [self, 'health']
	})
```
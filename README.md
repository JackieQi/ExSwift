# ExSwift

JavaScript inspired (lo-dash, underscore) set of Swift extensions for standard types, functions and classes.

## Contents ##

- [ExSwift](#exswift)
	- [Array](#array)
    	- [Instance Methods](#instance-methods)
		- [Class Methods](#class-methods)
		- [Operators](#operators)
    - [Int](#int)
    	- [Instance Methods](#instance-methods-1)
    	- [Class Methods](#class-methods-1)
    - [Float](#float)
    	- [Instance Methods](#instance-methods-2)
    	- [Class Methods](#class-methods-2)
    - [String](#string)
    	- [Instance Methods](#instance-methods-3)
		- [Class Methods](#class-methods-3)
		- [Operators](#operators-1)
    - [Range](#range)
    	- [Instance Methods](#instance-methods-4)
    - [Dictionary](#dictionary)
    	- [Instance Methods](#instance-methods-5)

### Array ###
Examples in [Examples/Array.md](Examples/Array.md)

##### Instance Methods #####

Name | Signature
---- | ---------
**`first`**|`first () -> T?`
**`last`**|`last () -> T?`
**`get`**|`get (index: Int) -> T?`
**`remove`**|`remove <U: Equatable> (element: U)`
**`take`**|`take (n: Int) -> Array<T>`
**`contains`**|`contains <T: Equatable> (item: T) -> Bool`
**`difference`**|`difference <T: Equatable> (values: Array<T>...) -> Array<T>`
**`intersection`**|`func intersection <U: Equatable> (values: Array<U>...) -> Array<T>`
**`union`**|`func union <U: Equatable> (values: Array<U>...) -> Array<T>`
**`unique`**|`unique <T: Equatable> () -> Array<T>`
**`indexOf`**|`func indexOf <T: Equatable> (item: T) -> Int`
**`zip`**|`zip (arrays: Array<Any>...) -> Array<Array<Any?>>`
**`shuffle`**|`shuffle ()`
**`shuffled`**|`shuffled () -> Array<T>`
**`sample`** *(random)*|`sample (size n: Int = 1) -> Array<T>`
**`max`**|`max <T: Comparable> () -> T`
**`min`**|`min <T: Comparable> () -> T`
**`each`**|`each (call: (T) -> ())`<br>`each (call: (Int, T) -> ())`
**`any`**|`any (call: (T) -> Bool) -> Bool`
**`all`**|`all (call: (T) -> Bool) -> Bool`
**`reject`**|`reject (exclude: (T -> Bool)) -> Array<T>`
**`pop`**|`pop() -> T`
**`push`**|`push(newElement: T)`
**`shift`**|`shift() -> T`
**`unshift`**|`unshift(newElement: T)`
**`groupBy`**|`groupBy <U> (groupingFunction group: (T) -> (U)) -> Dictionary<U, Array<T>>`

##### Class Methods #####

Name | Signatures
---- | ----------
**`range`**|`range <U: ForwardIndex> (range: Range<U>) -> Array<U>`

##### Operators #####
Name | Signature | Function
---- | --------- | --------
`-`|`<T: Equatable> (first: Array<T>, second: Array<T>) -> Array<T>`|Difference
`&`|`<T: Equatable> (first: Array<T>, second: Array<T>) -> Array<T>`|Intersection
<code>&#124;</code>|`<T: Equatable> (first: Array<T>, second: Array<T>) -> Array<T>`|Union
`[x..y]`<br>`[x...y]`|`subscript(range: Range<Int>) -> Array<T>`|Returns the sub-array from index *x* to index *y*

### Int ###
Examples in [Examples/Int.md](Examples/Int.md)

##### Instance Methods #####

Name | Signatures
---- | ----------
**`times`**|`times <T> (call: (Int) -> T)`<br>`times <T> (call: () -> T)`<br>`times (call: () -> ())`
**`after`**|`after <T> (call: () -> T) -> (() -> T?)`
**`isEven`**|`isEven () -> Bool`
**`isOdd`**|`idOdd () -> Bool`
**`upTo`**|`upTo (limit: Int, call: (Int) -> ())`
**`downTo`**|`downTo (limit: Int, call: (Int) -> ())`

##### Class Methods #####

Name | Signatures
---- | ----------
**`random`**|`random(min: Int = 0, max: Int) -> Int`


### Float ###
##### Instance Methods #####

Name | Signature
---- | ---------
**`abs`**|`abs () -> Float`

##### Class Methods #####

Name | Signatures | Usage
---- | ---------- | -----
**`random`**|`random(min: Float = 0, max: Float) -> Float`|`Float.random(min: 1, max: 1000)`

### String ###
Examples in [Examples/String.md](Examples/String.md)

##### Instance Methods #####

Name | Signature
---- | ---------
**`length`**|`length () -> Int`

##### Class Methods #####

Name | Signature
---- | ---------
**`random`**|`func random (var length len: Int = 0, charset: String = "...") -> String`

##### Operators #####
Name | Signature
---- | ---------
`[x]`|`subscript(index: Int) -> String?`
`[x..y]`<br>`[x...y]`|`subscript(range: Range<Int>) -> String`
`S * n`|`* (first: String, second: Int) -> String`

### Range ###
##### Instance Methods #####

Name | Signatures | Usage
---- | ---------- | -------
**`times`**|`times (call: (T) -> ())`<br>`times (call: () -> ())`|`(2..4).times({ (index: Int) in println(index) })`<br>`(2..4).times({ println("Hi") })`
**`each`**|`each (call: (T) -> ())`|`(2..4).each({ (index: Int) in println(index) })`

##### Operators #####
Name | Signature|Function
---- | ---------|--------
`=`|`== <U: ForwardIndex> (first: Range<U>, second: Range<U>) -> Bool`|Compares 2 ranges

### Dictionary ###
Examples in [Examples/Dictionary.md](Examples/Dictionary.md)

##### Instance Methods #####

Name | Signatures
---- | ----------
**`has`**|`has (key: KeyType) -> Bool`
**`isEmpty`**|`isEmpty () -> Bool`
**`map`**|`map(mapFunction map: (KeyType, ValueType) -> (KeyType, ValueType)) -> Dictionary<KeyType, ValueType>`
**`mapValues`**|`mapValues(mapFunction map: (KeyType, ValueType) -> (ValueType)) -> Dictionary<KeyType, ValueType>`
**`each`**|`each(eachFunction each: (KeyType, ValueType) -> ())`
**`filter`**|`filter(testFunction test: (KeyType, ValueType) -> Bool) -> Dictionary<KeyType, ValueType>`
**`merge`**|`merge (dictionaries: Dictionary<KeyType, ValueType>...) -> Dictionary<KeyType, ValueType>`
**`shift`**|`shift () -> (KeyType, ValueType)`
**`groupBy`**|`groupBy <T> (groupingFunction group: (KeyType, ValueType) -> (T)) -> Dictionary<T, Array<ValueType>>`
**`any`**|`any (test: (KeyType, ValueType) -> (Bool)) -> Bool`
**`all`**|`all (test: (KeyType, ValueType) -> (Bool)) -> Bool`

### To Do ###
* Compile as library as soon as XCode 6 stops crashing.
* Benchmark
* ...
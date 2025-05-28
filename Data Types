# មេរៀន៖ Data Types និង Type Casting ក្នុង Dart

## គោលបំណង
ស្វែងយល់ពី **data types** សំខាន់ៗក្នុង Dart របៀបប្រើប្រាស់ពួកវា និងវិធីធ្វើ **type casting** (ការប្តូរប្រភេទទិន្នន័យ) ដើម្បីប្តូរទិន្នន័យពីប្រភេទមួយទៅប្រភេទមួយទៀត។ មេរៀននេះរួមបញ្ចូលលំហាត់អនុវត្តដើម្បីពង្រឹងការរៀន។

## ១. សេចក្តីណែនាំអំពី Data Types
ក្នុង Dart, **data types** កំណត់ប្រភេទទិន្នន័យដែលអថេរអាចផ្ទុក។ Dart គឺជាភាសា **statically typed** មានន័យថាអ្នកត្រូវបញ្ជាក់ប្រភេទទិន្នន័យនៃអថេរនៅពេលប្រកាស ឬអនុញ្ញាតឱ្យ Dart សន្និដ្ឋានវាដោយប្រើ `var`, `final`, ឬ `const`។ **Type casting** គឺជាដំណើរការប្តូរទិន្នន័យពីប្រភេទមួយទៅប្រភេទមួយទៀត ដែលជួយឱ្យអ្នកធ្វើការជាមួយទិន្នន័យបានបត់បែនជាងមុន។

### ប្រភេទ Data Types សំខាន់ៗក្នុង Dart
1. **Numbers** (`int`, `double`)
2. **String**
3. **Boolean**
4. **List**
5. **Map**
6. **Set**
7. **Null**

## ២. ពិនិត្យលម្អិតអំពី Data Types និង Type Casting

### ២.១ Numbers
**Numbers** ក្នុង Dart មានពីរប្រភេទ៖
- **int**: ចំនួនគត់ (integer) ដូចជា 1, 42, -10។
- **double**: ចំនួនទសភាគ (floating-point) ដូចជា 3.14, -0.5។

#### ការប្រើប្រាស់
**int** និង **double** ត្រូវបានប្រើសម្រាប់ការគណនាគណិតវិទ្យា។ អ្នកអាចប្រើប្រតិបត្តិករ (`+`, `-`, `*`, `/`) ដើម្បីធ្វើការជាមួយ **Numbers**។

#### ឧទាហរណ៍
```dart
void main() {
  int age = 25;
  double height = 1.75;
  print('Age: $age, Height: $height'); // Output: Age: 25, Height: 1.75
}
```

#### Type Casting សម្រាប់ Numbers
- **int ទៅ double**: ប្រើមេថូដ `toDouble()`។
- **double ទៅ int**: ប្រើមេថូដ `toInt()` (កាត់ផ្នែកទសភាគ) ឬ `round()`, `ceil()`, `floor()` សម្រាប់ការបង្គត់។
- **String ទៅ int ឬ double**: ប្រើ `int.parse()` ឬ `double.parse()`។
- **int ឬ double ទៅ String**: ប្រើមេថូដ `toString()`។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  int count = 42;
  double countAsDouble = count.toDouble(); // int ទៅ double
  print(countAsDouble); // Output: 42.0

  double price = 19.99;
  int priceAsInt = price.toInt(); // double ទៅ int
  print(priceAsInt); // Output: 19

  String numberStr = '123';
  int parsedInt = int.parse(numberStr); // String ទៅ int
  double parsedDouble = double.parse('45.67'); // String ទៅ double
  print(parsedInt); // Output: 123
  print(parsedDouble); // Output: 45.67

  String ageStr = count.toString(); // int ទៅ String
  print('Age as string: $ageStr'); // Output: Age as string: 42
}
```

#### ចំណាំ
- ប្រយ័ត្ននឹងកំហុសនៅពេលប្រើ `int.parse()` ឬ `double.parse()` ប្រសិនបើ **String** មិនមែនជាទម្រង់លេខត្រឹមត្រូវ។ ប្រើ `tryParse()` ដើម្បីជៀសវាងកំហុស។
```dart
int? parsed = int.tryParse('abc'); // Returns null if invalid
print(parsed); // Output: null
```

### ២.២ String
**String** ត្រូវបានប្រើដើម្បីផ្ទុកអត្ថបទ។ អ្នកអាចប្រើសញ្ញា `' '` ឬ `" "` និង **String interpolation** (`$variable`) ដើម្បីបញ្ចូលអថេរក្នុង **String**។

#### ការប្រើប្រាស់
**String** គាំទ្រមេថូដដូចជា `length`, `toUpperCase()`, `toLowerCase()`, និង `substring()`។

#### ឧទាហរណ៍
```dart
void main() {
  String name = 'Sokha';
  String greeting = "Hello, $name!";
  print(greeting); // Output: Hello, Sokha!
  print(name.length); // Output: 5
}
```

#### Type Casting សម្រាប់ String
- **Number (int, double) ទៅ String**: ប្រើ `toString()`។
- **String ទៅ int ឬ double**: ប្រើ `int.parse()` ឬ `double.parse()`។
- **Boolean ទៅ String**: ប្រើ `toString()`។
- **String ទៅ Boolean**: ត្រូវបង្កើតលក្ខខណ្ឌផ្ទាល់ខ្លួន (ឧ. ពិនិត្យ "true" ឬ "false")។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  int age = 30;
  String ageStr = age.toString(); // int ទៅ String
  print(ageStr); // Output: 30

  String numberStr = '42.5';
  double number = double.parse(numberStr); // String ទៅ double
  print(number); // Output: 42.5

  bool isActive = true;
  String boolStr = isActive.toString(); // Boolean ទៅ String
  print(boolStr); // Output: true

  String boolInput = 'true';
  bool parsedBool = boolInput.toLowerCase() == 'true'; // String ទៅ Boolean
  print(parsedBool); // Output: true
}
```

### ២.៣ Boolean
**Boolean** ផ្ទុកតម្លៃ `true` ឬ `false` ហើយត្រូវបានប្រើសម្រាប់លក្ខខណ្ឌ។

#### ការប្រើប្រាស់
**Boolean** ត្រូវបានប្រើក្នុង **if**, **while**, ឬ **ternary operators**។

#### ឧទាហរណ៍
```dart
void main() {
  bool isStudent = true;
  bool hasJob = false;
  print('Is student? $isStudent'); // Output: Is student? true
  print('Has job? $hasJob'); // Output: Has job? false
}
```

#### Type Casting សម្រាប់ Boolean
- **String ទៅ Boolean**: ពិនិត្យតម្លៃ **String** (ឧ. "true" ឬ "false")។
- **Number ទៅ Boolean**: ប្រើលក្ខខណ្ឌ (ឧ. លេខមិនស្មើ 0 គឺ `true`)។
- **Boolean ទៅ String**: ប្រើ `toString()`។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  String boolStr = 'true';
  bool isTrue = boolStr.toLowerCase() == 'true'; // String ទៅ Boolean
  print(isTrue); // Output: true

  int number = 1;
  bool numberToBool = number != 0; // Number ទៅ Boolean
  print(numberToBool); // Output: true

  bool isActive = false;
  String boolToStr = isActive.toString(); // Boolean ទៅ String
  print(boolToStr); // Output: false
}
```

### ២.៤ List
**List** គឺជាបណ្តុំនៃធាតុដែលរៀបចំជាលំដាប់។ វាអាចផ្ទុកទិន្នន័យប្រភេទដូចគ្នា ឬផ្សេងគ្នា (ប្រសិនបើប្រើ `List<dynamic>`)។

#### ការប្រើប្រាស់
**List** គាំទ្រមេថូដដូចជា `add()`, `remove()`, `length`, និង **indexing** (`[0]`)។

#### ឧទាហរណ៍
```dart
void main() {
  List<String> fruits = ['Apple', 'Banana', 'Orange'];
  print(fruits[0]); // Output: Apple
  fruits.add('Mango');
  print(fruits); // Output: [Apple, Banana, Orange, Mango]
}
```

#### Type Casting សម្រាប់ List
- **List ទៅ Set**: ប្រើ `toSet()` ដើម្បីប្តូរទៅ **Set** (លុបធាតុស្ទួន)។
- **List ទៅ String**: ប្រើ `join()` ឬ `toString()`។
- **String ទៅ List**: ប្រើ `split()` ឬបង្កើត **List** ដោយផ្ទាល់។
- **List<dynamic> ទៅ List<specific type>**: ប្រើ `cast()` ឬ `map()`។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  List<String> fruits = ['Apple', 'Apple', 'Banana'];
  Set<String> fruitSet = fruits.toSet(); // List ទៅ Set
  print(fruitSet); // Output: {Apple, Banana}

  String fruitStr = fruits.join(', '); // List ទៅ String
  print(fruitStr); // Output: Apple, Apple, Banana

  String csv = 'Cat,Dog,Bird';
  List<String> animals = csv.split(','); // String ទៅ List
  print(animals); // Output: [Cat, Dog, Bird]

  List<dynamic> mixed = [1, '2', 3];
  List<int> integers = mixed.map((e) => int.parse(e.toString())).toList(); // List<dynamic> ទៅ List<int>
  print(integers); // Output: [1, 2, 3]
}
```

### ២.៥ Map
**Map** ផ្ទុកទិន្នន័យជាគូ **key-value**។ **Key** និង **value** អាចមានប្រភេទទិន្នន័យណាមួយ។

#### ការប្រើប្រាស់
**Map** គាំទ្រមេថូដដូចជា `putIfAbsent()`, `remove()`, និង **key access** (`map[key]`)។

#### ឧទាហរណ៍
```dart
void main() {
  Map<String, int> scores = {
    'Sokha': 85,
    'Vichea': 90,
  };
  print(scores['Sokha']); // Output: 85
  scores['Ratha'] = 88;
  print(scores); // Output: {Sokha: 85, Vichea: 90, Ratha: 88}
}
```

#### Type Casting សម្រាប់ Map
- **Map ទៅ List**: ប្រើ `keys.toList()` ឬ `values.toList()`។
- **Map ទៅ String**: ប្រើ `toString()` ឬបង្កើត **String** ផ្ទាល់ខ្លួន។
- **List ទៅ Map**: ប្រើ `asMap()` ឬបង្កើត **Map** ដោយផ្ទាល់។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  Map<String, int> scores = {'Sokha': 85, 'Vichea': 90};
  List<String> names = scores.keys.toList(); // Map ទៅ List (keys)
  print(names); // Output: [Sokha, Vichea]

  List<int> grades = scores.values.toList(); // Map ទៅ List (values)
  print(grades); // Output: [85, 90]

  String mapStr = scores.toString(); // Map ទៅ String
  print(mapStr); // Output: {Sokha: 85, Vichea: 90}

  List<String> fruits = ['Apple', 'Banana'];
  Map<int, String> fruitMap = fruits.asMap(); // List ទៅ Map
  print(fruitMap); // Output: {0: Apple, 1: Banana}
}
```

### ២.៦ Set
**Set** គឺជាបណ្តុំនៃធាតុដែលមិនស្ទួនគ្នា និងមិនមានលំដាប់។

#### ការប្រើប្រាស់
**Set** គាំទ្រមេថូដដូចជា `add()`, `remove()`, និង `contains()`។

#### ឧទាហរណ៍
```dart
void main() {
  Set<String> colors = {'Red', 'Blue', 'Green'};
  colors.add('Red'); // មិនបន្ថែមទេ ព្រោះ Red មានរួចហើយ
  print(colors); // Output: {Red, Blue, Green}
}
```

#### Type Casting សម្រាប់ Set
- **Set ទៅ List**: ប្រើ `toList()`។
- **List ទៅ Set**: ប្រើ `toSet()`។
- **Set ទៅ String**: ប្រើ `toString()` ឬ `join()`។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  Set<String> colors = {'Red', 'Blue', 'Green'};
  List<String> colorList = colors.toList(); // Set ទៅ List
  print(colorList); // Output: [Red, Blue, Green]

  List<String> fruits = ['Apple', 'Apple', 'Banana'];
  Set<String> fruitSet = fruits.toSet(); // List ទៅ Set
  print(fruitSet); // Output: {Apple, Banana}

  String colorStr = colors.join(', '); // Set ទៅ String
  print(colorStr); // Output: Red, Blue, Green
}
```

### ២.៧ Null
**Null** តំណាងឱ្យតម្លៃដែលមិនមាន។ Dart គាំទ្រ **null safety** ដែលទាមទារឱ្យអ្នកបញ្ជាក់អថេរដែលអាចជា `null` ដោយប្រើ `?`។

#### ការប្រើប្រាស់
**Null** ត្រូវបានប្រើនៅពេលអថេរមិនទាន់មានតម្លៃ។ **Null safety** ជួយការពារកំហុស។

#### ឧទាហរណ៍
```dart
void main() {
  String? nickname;
  print(nickname); // Output: null
  nickname = 'Sok';
  print(nickname); // Output: Sok
}
```

#### Type Casting និង Null
- **Null** មិនអាចប្តូរទៅប្រភេទផ្សេងដោយផ្ទាល់បានទេ ប៉ុន្តែអ្នកអាចប្រើ **null checks** ឬ **default values**។
- ប្រើ `??` ដើម្បីផ្តល់ **default value** ឬ `!` នៅពេលប្រាកដថាអថេរមិនមែនជា `null`។

#### ឧទាហរណ៍ Type Casting
```dart
void main() {
  String? input;
  String result = input ?? 'Unknown'; // Default value if null
  print(result); // Output: Unknown

  String? name = 'Vichea';
  String definiteName = name!; // Assert non-null
  print(definiteName); // Output: Vichea
}
```

## ៣. ការប្រើប្រាស់ var, final, និង const
- **`var`**: សន្និដ្ឋានប្រភេទទិន្នន័យដោយស្វ័យប្រវត្តិ។
- **`final`**: អថេរដែលអាចកំណត់តម្លៃបានតែម្តងគត់។
- **`const`**: អថេរដែលមានតម្លៃថេរនៅពេលចងក្រង។

#### ឧទាហរណ៍
```dart
void main() {
  var name = 'Sokha'; // String
  final int age = 20; // មិនអាចផ្លាស់ប្តូរបន្ទាប់ពីកំណត់
  const double pi = 3.14; // ថេរនៅពេលចងក្រង
  print('Name: $name, Age: $age, Pi: $pi');
}
```

#### Type Casting ជាមួយ var, final, const
- **var** អនុញ្ញាតឱ្យអ្នកផ្លាស់ប្តូរតម្លៃ ប៉ុន្តែប្រភេទទិន្នន័យត្រូវតែនៅដដែល។
- **final** និង **const** មិនអនុញ្ញាតឱ្យផ្លាស់ប្តូរតម្លៃទេ ដូច្នេះ **type casting** ត្រូវធ្វើនៅពេលប្រកាស។

#### ឧទាហរណ៍
```dart
void main() {
  var value = '42';
  int parsedValue = int.parse(value); // String ទៅ int
  print(parsedValue); // Output: 42

  final String numberStr = '3.14';
  final double number = double.parse(numberStr); // String ទៅ double
  print(number); // Output: 3.14
}
```

## ៤. លំហាត់អនុវត្ត
សរសេរ **program** ក្នុង Dart ដែល៖
- ប្រកាសអថេរដើម្បីផ្ទុកឈ្មោះ (String), អាយុជា **String** (ឧ. "25"), និងទម្ងន់ជា **String** (ឧ. "65.5")។
- ប្តូរ (**cast**) អាយុទៅ **int** និងទម្ងន់ទៅ **double**។
- បង្កើត **List** ដើម្បីផ្ទុកចំណូលចិត្តអាហារបីប្រភេទ និងប្តូរវាទៅ **Set**។
- បង្កើត **Map** ដើម្បីផ្ទុកពិន្ទុសម្រាប់មុខវិជ្ជាពីរផ្សេងគ្នា និងប្តូរតម្លៃ (**values**) ទៅ **List**។
- ប្រើ **Boolean** ដើម្បីបញ្ជាក់ថាតើបុគ្គលនោះជាសិស្សឬអត់ និងប្តូរវាទៅ **String**។
- បោះពុម្ពទិន្នន័យទាំងអស់នេះ។

### ដំណោះស្រាយ
```dart
void main() {
  String name = 'Vichea';
  String ageStr = '22';
  String weightStr = '65.5';
  
  int age = int.parse(ageStr); // String ទៅ int
  double weight = double.parse(weightStr); // String ទៅ double
  
  List<String> favoriteFoods = ['Pizza', 'Sushi', 'Pizza'];
  Set<String> uniqueFoods = favoriteFoods.toSet(); // List ទៅ Set
  
  Map<String, int> grades = {'Math': 95, 'Science': 88};
  List<int> gradeList = grades.values.toList(); // Map ទៅ List
  
  bool isStudent = true;
  String isStudentStr = isStudent.toString(); // Boolean ទៅ String

  print('Name: $name');
  print('Age: $age');
  print('Weight: $weight kg');
  print('Unique Foods: $uniqueFoods');
  print('Grades List: $gradeList');
  print('Is Student? $isStudentStr');
}
```

#### លទ្ធផល
```
Name: Vichea
Age: 22
Weight: 65.5 kg
Unique Foods: {Pizza, Sushi}
Grades List: [95, 88]
Is Student? true
```

## ៥. ការអនុវត្តល្អបំផុត
- **បញ្ជាក់ប្រភេទទិន្នន័យ**៖ ប្រើ **explicit types** (ដូចជា `int`, `String`) ដើម្បីធ្វើឱ្យកូដច្បាស់លាស់។
- **ប្រើ null safety**៖ ប្រើ `?` សម្រាប់អថេរដែលអាចជា `null` និង `!` នៅពេលប្រាកដថាវាមិនមែនជា `null`។
- **ប្រើ tryParse សម្រាប់ parsing**៖ ដើម្បីជៀសវាងកំហុសនៅពេលប្តូរ **String** ទៅ **int** ឬ **double**។
- **ជ្រើសរើសប្រភេទទិន្នន័យសមស្រប**៖ ប្រើ **List** សម្រាប់បណ្តុំដែលមានលំដាប់, **Map** សម្រាប់គូ **key-value**, និង **Set** សម្រាប់ធាតុមិនស្ទួន។
- **ប្រយ័ត្ននឹង Type Casting**៖ ត្រូវប្រាកដថាទិន្នន័យមានទម្រង់ត្រឹមត្រូវមុននឹងធ្វើ **casting** (ឧ. ពិនិត្យ **String** មុននឹងប្រើ `parse`)។

## ៦. សង្ខេប
- Dart មាន **data types** សំខាន់ៗដូចជា **int**, **double**, **String**, **Boolean**, **List**, **Map**, និង **Set**។
- **Type casting** អនុញ្ញាតឱ្យអ្នកប្តូរទិន្នន័យពីប្រភេទមួយទៅប្រភេទមួយទៀត ដោយប្រើមេថូដដូចជា `toString()`, `parse()`, `toList()`, `toSet()`។
- **Null safety** ជួយគ្រប់គ្រងតម្លៃ `null` ប្រកបដោយសុវត្ថិភាព។
- ប្រើ `var`, `final`, ឬ `const` ដើម្បីគ្រប់គ្រងអថេរប្រកបដោយប្រសិទ្ធភាព។

## ៧. ការអានបន្ថែម
- [Dart Official Documentation: Types and Type System](https://dart.dev/guides/language/language-tour#types-and-type-system)
- អនុវត្តជាមួយ **data types** និង **type casting** នៅលើ [DartPad](https://dartpad.dev)។

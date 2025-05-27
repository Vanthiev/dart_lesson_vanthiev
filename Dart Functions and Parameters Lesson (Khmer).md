# មេរៀន៖ Functions និង Function Parameters ក្នុង Dart

## គោលបំណង
ស្វែងយល់ពីរបៀបកំណត់ និងប្រើ **functions** ក្នុង Dart ដោយផ្តោតលើប្រភេទផ្សេងៗនៃ **parameters**។

## ១. សេចក្តីណែនាំអំពី Functions ក្នុង Dart
**Function** ក្នុង Dart គឺជាបណ្តុំកូដដែលអាចប្រើឡើងវិញបាន ដើម្បីអនុវត្តកិច្ចការជាក់លាក់មួយ។ **Functions** អាចទទួល **inputs (parameters)** ដំណើរការពួកវា និងបញ្ជូន **output** មួយ។ វាជួយធ្វើឱ្យកូដមានលក្ខណៈជាបណ្តុំ និងងាយស្រួលថែទាំ។

### វាក្យសម្ព័ន្ធ Function មូលដ្ឋាន
```dart
returnType functionName(parameter1, parameter2) {
  // Function body
  return result; // Optional
}
```

- **returnType**: ប្រភេទទិន្នន័យនៃតម្លៃដែល **function** បញ្ជូនត្រឡប់ (ប្រើ `void` ប្រសិនបើមិនបញ្ជូនអ្វីត្រឡប់)។
- **functionName**: ឈ្មោះរបស់ **function**។
- **parameters**: **Inputs** ទៅកាន់ **function** (ជាជម្រើស)។
- **function body**: កូដដែលដំណើរការនៅពេល **function** ត្រូវបានហៅ។

### ឧទាហរណ៍៖ Function មូលដ្ឋាន
```dart
void greet(String name) {
  print('Hello, $name!');
}

void main() {
  greet('Alice'); // Output: Hello, Alice!
}
```

## ២. ប្រភេទនៃ Function Parameters ក្នុង Dart
Dart គាំទ្រប្រភេទ **parameters** ជាច្រើន ដើម្បីធ្វើឱ្យ **functions** មានភាពបត់បែន និងមានអានុភាព។ ទាំងនេះរួមមាន **required**, **optional positional**, **optional named**, និង **default parameters**។

### ២.១ Required Parameters
**Required parameters** គឺជា **parameters** ដែលត្រូវតែផ្តល់ឱ្យនៅពេលហៅ **function**។

#### ឧទាហរណ៍
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  print(add(5, 3)); // Output: 8
}
```
- `a` និង `b` គឺជា **required parameters**។ អ្នកត្រូវតែផ្តល់ចំនួនគត់ពីរនៅពេលហៅ `add`។

### ២.២ Optional Positional Parameters
**Optional positional parameters** ត្រូវបានដាក់ក្នុងតង្កៀបការ៉េ `[]` ហើយមិនចាំបាច់ទេ។ ប្រសិនបើមិនបានផ្តល់ ពួកវានឹងមានតម្លៃ `null`។

#### វាក្យសម្ព័ន្ធ
```dart
returnType functionName(requiredParam, [optionalParam]) {
  // Function body
}
```

#### ឧទាហរណ៍
```dart
String describePerson(String name, [int? age]) {
  if (age != null) {
    return '$name is $age years old.';
  }
  return '$name has no age specified.';
}

void main() {
  print(describePerson('Bob')); // Output: Bob has no age specified.
  print(describePerson('Alice', 25)); // Output: Alice is 25 years old.
}
```
- `age` គឺជា **optional**។ ប្រសិនបើមិនបានផ្តល់ វានឹងមានតម្លៃ `null`។

### ២.៣ Optional Named Parameters
**Named parameters** ត្រូវបានដាក់ក្នុងតង្កៀបវង់ `{}` ហើយជា **optional**។ ពួកវាអនុញ្ញាតឱ្យអ្នកបញ្ជាក់ **parameters** ដោយឈ្មោះនៅពេលហៅ **function** ដែលធ្វើឱ្យកូដកាន់តែងាយយល់។

#### វាក្យសម្ព័ន្ធ
```dart
returnType functionName(requiredParam, {namedParam}) {
  // Function body
}
```

#### ឧទាហរណ៍
```dart
String introduce(String name, {String? greeting, String? title}) {
  greeting ??= 'Hi'; // Default to 'Hi' if greeting is null
  title ??= ''; // Default to empty string if title is null
  return '$greeting, $title $name!';
}

void main() {
  print(introduce('Charlie')); // Output: Hi,  Charlie!
  print(introduce('Alice', greeting: 'Hello', title: 'Dr.')); // Output: Hello, Dr. Alice!
}
```
- `greeting` និង `title` គឺជា **named parameters**។ អ្នកអាចផ្តល់ពួកវាតាមលំដាប់ណាមួយដោយប្រើឈ្មោះរបស់ពួកវា។

### ២.៤ Default Parameters
ទាំង **optional positional** និង **named parameters** អាចមាន **default values** ដែលត្រូវបានប្រើប្រសិនបើ **parameter** មិនត្រូវបានផ្តល់។

#### ឧទាហរណ៍៖ Default Named Parameters
```dart
void printOrder(String item, {int quantity = 1, String currency = 'USD'}) {
  print('Ordered: $quantity $item(s) in $currency');
}

void main() {
  printOrder('Book'); // Output: Ordered: 1 Book(s) in USD
  printOrder('Pen', quantity: 5, currency: 'EUR'); // Output: Ordered: 5 Pen(s) in EUR
}
```

#### ឧទាហរណ៍៖ Default Positional Parameters
```dart
String createMessage(String recipient, [String greeting = 'Hello']) {
  return '$greeting, $recipient!';
}

void main() {
  print(createMessage('Dave')); // Output: Hello, Dave!
  print(createMessage('Eve', 'Hi')); // Output: Hi, Eve!
}
```

### ២.៥ Required Named Parameters
អ្នកអាចធ្វើឱ្យ **named parameters** ក្លាយជាចាំបាច់ដោយប្រើពាក្យគន្លឹះ `required`។

#### ឧទាហរណ៍
```dart
void registerUser({required String username, String? email}) {
  print('Registered: $username, Email: ${email ?? "Not provided"}');
}

void main() {
  registerUser(username: 'Frank'); // Output: Registered: Frank, Email: Not provided
  registerUser(username: 'Grace', email: 'grace@example.com'); // Output: Registered: Grace, Email: grace@example.com
}
```
- `username` គឺជា **required named parameter** ដូច្នេះវាត្រូវតែផ្តល់ឱ្យ។

## ៣. ការអនុវត្តល្អបំផុតសម្រាប់ Function Parameters
- **ប្រើ named parameters ដើម្បីភាពច្បាស់លាស់**៖ នៅពេល **function** មាន **optional parameters** ច្រើន ការ **named parameters** ធ្វើឱ្យកូដកាន់តែងាយយល់។
- **ផ្តល់ default values នៅពេលសមស្រប**៖ នេះជួយកាត់បន្ថយតម្រូវការ **null checks** និងធ្វើឱ្យ **functions** ងាយស្រួលប្រើ។
- **ប្រើ required named parameters សម្រាប់ inputs សំខាន់**៖ នេះធានាថា **parameters** សំខាន់ត្រូវបានផ្តល់ជានិច្ច ខណៈពេលដែលរក្សាភាពបត់បែននៃ **named parameters**។
- **រក្សា functions ឱ្យផ្តោត**៖ **Function** គួរតែធ្វើរឿងតែមួយឱ្យល្អ។ ជៀសវាង **parameters** ច្រើនពេក ព្រោះវាអាចបង្ហាញថា **function** កំពុងធ្វើច្រើនពេក។

## ៤. លំហាត់អនុវត្ត
សរសេរ **function** ក្នុង Dart ដែលគណនាតម្លៃសរុបនៃទំនិញក្នុងរទេះទិញទំនិញ។ **Function** នេះគួរតែ៖
- ទទួល **required parameter** សម្រាប់តម្លៃទំនិញ។
- ទទួល **optional named parameter** សម្រាប់អត្រាពន្ធ (default ទៅ 0.1 ពោលគឺ 10%)។
- ទទួល **optional positional parameter** សម្រាប់បរិមាណ (default ទៅ 1)។
- បញ្ជូនតម្លៃសរុបជា **double**។

### ដំណោះស្រាយ
```dart
double calculateTotal(double price, [int quantity = 1, double taxRate = 0.1]) {
  double subtotal = price * quantity;
  double tax = subtotal * taxRate;
  return subtotal + tax;
}

void main() {
  print(calculateTotal(20.0)); // Output: 22.0 (20 + 10% tax)
  print(calculateTotal(20.0, 2)); // Output: 44.0 (40 + 10% tax)
  print(calculateTotal(20.0, 2, 0.2)); // Output: 48.0 (40 + 20% tax)
}
```

## ៥. សង្ខេប
- **Functions** ក្នុង Dart ត្រូវបានកំណត់ជាមួយ **return type**, **name**, និង **parameters** (ជាជម្រើស)។
- **Parameters** អាចជា **required**, **optional positional**, **optional named**, ឬមាន **default values**។
- ប្រើ `required` សម្រាប់ **named parameters** ដែលចាំបាច់។
- ជ្រើសរើសប្រភេទ **parameters** ដោយផ្អែកលើគោលបំណង និងភាពងាយស្រួលនៃការអានរបស់ **function**។

## ៦. ការអានបន្ថែម
- [Dart Official Documentation: Functions](https://dart.dev/guides/language/language-tour#functions)
- អនុវត្តការសរសេរ **functions** ជាមួយប្រភេទ **parameters** ផ្សេងៗនៅលើ [DartPad](https://dartpad.dev)។
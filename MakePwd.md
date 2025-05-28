# 🛡️ Dart Random Password Generator

A complete guide to generating secure random passwords in Dart. Save this entire file as `password_generator.md` for documentation.

```dart
import 'dart:math';

void main() {
  // Generate a cryptographically-strong random password
  String generatePassword({
    required int length,
    bool includeUppercase = true,
    bool includeLowercase = true,
    bool includeNumbers = true,
    bool includeSymbols = false,
  }) {
    String chars = '';
    if (includeUppercase) chars += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
    if (includeLowercase) chars += 'abcdefghijklmnopqrstuvwxyz';
    if (includeNumbers) chars += '0123456789';
    if (includeSymbols) chars += '!@#\$%^&*()_+-=[]{}|;:,.<>?';

    if (chars.isEmpty) throw ArgumentError('At least one character set must be enabled');
    
    final random = Random.secure();
    return List.generate(length, (_) => chars[random.nextInt(chars.length)]).join();
  }

  // Example usage
  final password = generatePassword(
    length: 16,
    includeSymbols: true,
  );
  
  print('🔒 Generated Password: $password');
}
```

## 🧩 Code Breakdown

### 1. Character Pool Configuration
```dart
String chars = '';
if (includeUppercase) chars += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';  // 26 chars
if (includeLowercase) chars += 'abcdefghijklmnopqrstuvwxyz';  // 26 chars
if (includeNumbers) chars += '0123456789';                   // 10 chars
if (includeSymbols) chars += '!@#\$%^&*()_+-=[]{}|;:,.<>?';  // 20+ chars
```
- Dynamically builds the character set based on parameters
- **Default**: Upper + Lower + Numbers (62 characters)
- **With Symbols**: Adds 20+ special characters

### 2. Secure Random Generation
```dart
final random = Random.secure();  // Cryptographically secure RNG
List.generate(length, (_) => chars[random.nextInt(chars.length)]).join();
```
- `Random.secure()` uses entropy from the OS (more secure than `Random()`)
- Generates a list of random indices, then joins into a string

### 3. Error Handling
```dart
if (chars.isEmpty) throw ArgumentError('At least one character set must be enabled');
```
- Prevents empty character sets which would crash the program

## 🚀 How to Use

1. **Save the code** as `password_generator.dart`
2. **Run it** with Dart:
   ```bash
   dart run password_generator.dart
   ```
3. **Example Output**:
   ```
   🔒 Generated Password: pA3!k9L$mZ2*qF@1
   ```

## ⚙️ Customization Options

### Change Password Length
```dart
generatePassword(length: 20)  // 20-character password
```

### Disable Character Sets
```dart
generatePassword(
  length: 12,
  includeUppercase: false,  // Only lowercase + numbers
)
```

### Stronger Passwords
```dart
generatePassword(
  length: 24,
  includeSymbols: true,  // Adds special characters
)
```

## 🔒 Security Best Practices

1. **Always use `Random.secure()`** for password generation
2. **Never log passwords** in production environments
3. **Minimum 12 characters** for basic security
4. **Combine with password strength meters** when users create passwords

## 📊 Character Set Math

| Configuration               | Possible Combinations |
|-----------------------------|----------------------|
| Upper + Lower + Numbers     | 62^12 ≈ 3.2e21       |
| With Symbols (82 chars)     | 82^12 ≈ 1.9e23       |
| 16-char with Symbols        | 82^16 ≈ 4.8e30       |

> For comparison: 1 trillion guesses/sec would take **152 million years** to crack 82^16

---

💡 **Pro Tip**: Add this to a Flutter app as a utility class for in-app password generation!
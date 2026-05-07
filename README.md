## 🧪 Testing

As the application grows, manual testing becomes difficult.
Automated testing ensures that the app works correctly before release while maintaining development speed.

---

## 📊 Types of Tests

### 🔹 Unit Tests

* Test a single function, method, or class
* Focus on business logic correctness
* Use mocking to isolate dependencies
* Fast execution and low maintenance

---

### 🔹 Widget Tests

* Test individual UI components (widgets)
* Verify UI rendering and user interactions
* Run in a simulated Flutter environment
* More comprehensive than unit tests

---

### 🔹 Integration Tests

* Test the full app or large features
* Cover real user flows
* Provide the highest confidence
* Slower and more complex

---

## ⚖️ Trade-offs

| Type        | Confidence | Maintenance | Dependencies | Speed |
| ----------- | ---------- | ----------- | ------------ | ----- |
| Unit        | Low        | Low         | Few          | Fast  |
| Widget      | Higher     | Medium      | More         | Fast  |
| Integration | Highest    | High        | Most         | Slow  |

---
# 🧪 Flutter Testing Lifecycle Guide

A clean and professional guide for understanding the Flutter/Dart testing lifecycle.

---

# 📌 Overview

Flutter testing provides lifecycle functions that help organize test preparation and cleanup.

These functions make tests:
- Cleaner
- More maintainable
- Easier to scale
- More professional

---

# ⚡ Lifecycle Functions

| Function | Purpose | Execution Time |
|----------|----------|----------------|
| `setUp()` | Prepare test data before each test | Before every test |
| `tearDown()` | Clean resources after each test | After every test |
| `setUpAll()` | Initialize heavy/shared resources once | Before all tests |
| `tearDownAll()` | Dispose shared resources once | After all tests |

---

# 🔹 `setUp()`

Runs before every single test.

Use it for repeated initialization logic.

## ✅ Best For
- Creating fresh instances
- Resetting variables
- Preparing mock objects
- Initializing repositories/services

## Example

```dart
setUp(() {
  userRepository = MockUserRepository();
});
```

---

# 🔹 `tearDown()`

Runs after every test.

Used to clean resources and reset states.

## ✅ Best For
- Clearing temporary data
- Closing streams
- Resetting states
- Removing listeners

## Example

```dart
tearDown(() {
  userRepository.dispose();
});
```

---

# 🔹 `setUpAll()`

Runs only once before all tests.

Ideal for heavy initialization.

## ✅ Best For
- Database initialization
- Dependency injection setup
- Starting shared services
- Loading large resources

## Example

```dart
setUpAll(() async {
  await initializeDatabase();
});
```

---

# 🔹 `tearDownAll()`

Runs once after all tests finish.

Used for final cleanup.

## ✅ Best For
- Closing databases
- Stopping services
- Releasing shared resources

## Example

```dart
tearDownAll(() async {
  await closeDatabase();
});
```

---

# 🎯 Golden Rule

> Use `setUp()` for repeated setup  
> Use `setUpAll()` for heavy initialization  
> Use `tearDown()` for cleanup after each test  
> Use `tearDownAll()` for final cleanup

---

# 🧩 Complete Example

```dart
void main() {

  setUpAll(() {
    print('🚀 Starting all tests');
  });

  setUp(() {
    print('✅ Before each test');
  });

  tearDown(() {
    print('🧹 After each test');
  });

  tearDownAll(() {
    print('🏁 Finished all tests');
  });

  test('Addition Test', () {
    expect(2 + 2, 4);
  });
}
```

---

# 📚 Quick Summary

| Function | Recommended Usage |
|----------|-------------------|
| `setUp()` | Repeated initialization |
| `tearDown()` | Cleanup after every test |
| `setUpAll()` | Heavy setup once |
| `tearDownAll()` | Final cleanup |

---

# 💡 Best Practices

- Keep tests isolated.
- Avoid shared mutable state.
- Use `setUp()` to ensure clean test environments.
- Prefer lightweight tests whenever possible.
- Use `setUpAll()` carefully to avoid dependency between tests.

---

# ✅ Benefits of Proper Lifecycle Usage

- Better test readability
- Easier maintenance
- Faster execution
- Cleaner architecture
- More reliable test results
  
## 🎯 Testing Strategy

* Focus on writing many **Unit Tests** for core logic
* Use **Widget Tests** for UI validation
* Add **Integration Tests** for critical user flows
* Track **Code Coverage** to ensure quality

---

## 🛠️ Run Tests

```bash
flutter test
```

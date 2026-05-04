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

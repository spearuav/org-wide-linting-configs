# 🚀 SpearUAV Centralized Linter Configs

This repository contains **standardized linting configurations** for all SpearUAV repositories.  
By using these shared configurations, we **ensure consistent code quality and style** across all projects.

---

## 📌 Configuration Files

### **Python (Flake8)**
📄 **`.flake8`**
- Enforces **critical error checks** (syntax errors, undefined names)
- Allows lines **up to 127 characters**
- Warns if **functions are too complex**
- Excludes unnecessary files (`.git`, `__pycache__`, etc.)

#### ✅ **How to Use**
- Manually:
  ```bash
  flake8 . --config=lint-configs/.flake8

---

### **C++ (Clang-Format)**
📄 **`.clang-format`**
- Based on **Google C++ style**
- Uses **4-space indentation**
- Matches **Flake8’s 127-character limit**
- Enforces **explicit multi-line if/else/loops**
- Keeps pointer alignment consistent (`int* ptr`)
- Auto-wraps comments and sorts includes

#### ✅ **How to Use**
- Manually:
  ```bash
  clang-format -i --style=file lint-configs/.clang-format **/*.cpp **/*.h
  ```
- In **GitHub Actions**:
  ```yaml
  - name: Run Clang-Format
    run: clang-format -i --style=file lint-configs/.clang-format **/*.cpp **/*.h
  ```

---

## 📌 How to Apply These Configurations in All Repositories

### **🔹 Option 1: Use Git Submodules**
Run this inside each repository:
```bash
git submodule add https://github.com/spearuav/org-wide-linting-configs lint-configs
```

### **🔹 Option 2: Auto-Fetch Configs in CI/CD**
Modify **`.github/workflows/lint.yml`**:
```yaml
- name: Fetch Linter Configs
  run: git clone https://github.com/spearuav/org-wide-linting-configs lint-configs
```

---

## 📌 Contributing
- Any updates to `.flake8` or `.clang-format` should be **made in this repository**.
- Repositories will automatically **pull the latest settings**.

---

## 📌 Contact
For any issues, contact the **System Validation Team** at SpearUAV.



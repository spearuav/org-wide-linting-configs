# 🚀 SpearUAV Centralized Linter Configs

This repository contains **standardized linting configurations** for all SpearUAV repositories.  
By using these shared configurations, we **ensure consistent code quality and style** across all projects.

Super-linter configuration can be found [here](https://github.com/super-linter/super-linter?tab=readme-ov-file#configure-super-linter)

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
- Based on **Microsoft C++ style**
- 4-space indentation
- 120-character column limit
- Enforces **explicit multi-line if/else/loops**
- Keeps pointer alignment consistent (`int *ptr`)

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

### **🔹 Option 1: Use as reusable workflow**
Reference the workflow file as a step
```yaml
  jobs:
    # ...

    lint:
      uses: spearuav/org-wide-linting-configs/.github/workflows/lint.yml@main
    # if you want other jobs to depend on successful linting
    # set the next step as dependent with "needs" as follows:
    another-job:
      needs: lint
      # ...
```

### **🔹 Option 2: Use Git Submodules**
Run this inside each repository:
```bash
git submodule add https://github.com/spearuav/org-wide-linting-configs lint-configs
```

---

## 📌 Contributing
- Any updates to `.flake8` or `.clang-format` should be **made in this repository**.
- Repositories will automatically **pull the latest settings**.

---

## 📌 Contact
For any issues, contact the **System Validation Team** at SpearUAV.



To list a directory as a **tree** in Bash (with subdirectories and files)

---

### ✅ Step-by-step Instructions

1. **Install `tree`** (if not already installed):

* **Ubuntu/Debian**:

  ```bash
  sudo apt install tree
  ```

* **CentOS/RHEL**:

  ```bash
  sudo yum install tree
  ```

* **macOS (with Homebrew)**:

  ```bash
  brew install tree
  ```

2. **Usage Examples**:

* List current directory as a tree:

  ```bash
  tree
  ```

* List a specific directory:

  ```bash
  tree /path/to/directory
  ```

* Show only directories (no files):

  ```bash
  tree -d
  ```

* Limit depth of directory display (e.g., 2 levels):

  ```bash
  tree -L 2
  ```

* Print hidden files too:

  ```bash
  tree -a
  ```

* Save output to a file (e.g., for documentation):

  ```bash
  tree -a -L 3 > directory-structure.txt
  ```

---

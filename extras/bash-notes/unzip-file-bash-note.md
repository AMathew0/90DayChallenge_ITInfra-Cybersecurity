---

### Extracting a GitHub Repo ZIP File Using Bash

#### Steps to Extract ZIP File:

1. **Navigate to the directory** where your `.zip` file is downloaded.

   ```bash
   cd /path/to/downloaded-file
   ```

2. **Extract the ZIP file** using the `unzip` command.
   Replace `your-repo.zip` with the actual name of your downloaded file.

   ```bash
   unzip your-repo.zip
   ```

   * This will extract the contents of the ZIP file to the current directory.

3. **Verify the extraction** by listing the extracted files.

   ```bash
   ls -l
   ```

#### Optional: If `unzip` is not installed, you can install it:

* On **Debian/Ubuntu**:

  ```bash
  sudo apt-get install unzip
  ```
* On **CentOS/Fedora**:

  ```bash
  sudo yum install unzip
  ```

#### 📂 Result:

The ZIP file contents will now be extracted to your current directory, and you can start using or modifying the repo files.

---

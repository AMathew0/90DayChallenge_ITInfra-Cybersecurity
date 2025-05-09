Create Multiple `.md` Files in Bash

#### ✅ Objective:

Generate `Day-01.md` to `Day-90.md` files using a simple Bash script.

#### 🧾 Bash Script:

```bash
for i in $(seq -w 1 90); do
  touch "Day-$i.md"
done
```

#### 📌 Explanation:

* `seq -w 1 90` → Generates numbers from `01` to `90` with leading zeros.
* `touch "Day-$i.md"` → Creates empty files: `Day-01.md`, `Day-02.md`, ..., `Day-90.md`.

#### 📂 Result:

A set of 90 markdown files created in your current directory.

---

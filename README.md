# 🐍 python-venv-helper

A tiny but mighty Bash script to make Python virtual environment management effortless — especially for macOS users who work with Python daily.

---

## 💡 What It Does

`python-venv-helper` simplifies the venv workflow.

No more remembering environment names or typing out long commands like:

```bash
python3 -m venv .venv
source .venv/bin/activate
which python
```

Instead, you just run:

```bash
source venv
```

The script will automatically:

1. ✅ Check if a virtual environment already exists in your current directory  
2. 🆕 Create one named `.venv` if it doesn’t  
3. ⚙️ Activate it  
4. 🐍 Show which Python executable is being used

---

## 🚀 Installation

1. Copy the script to your system path (e.g., `/usr/local/bin/`):

   ```bash
   sudo cp venv /usr/local/bin/venv
   ```

2. Make it executable:

   ```bash
   sudo chmod +x /usr/local/bin/venv
   ```

> 💡 **Tip:** On Apple Silicon / modern macOS, `/usr/local/bin` is typically in your `PATH`.  
> If not, you can use `/opt/homebrew/bin` or another directory in your path.

---

## 🧠 Usage

In any Python project directory, simply run:

```bash
source venv
```

The script will either create or activate your local virtual environment.

---

## 🧰 Example

```bash
$ cd ~/projects/mytool
source venv
Virtual environment not found. Creating a new one...
Virtual environment created successfully. Activating...
Upgrading pip to the latest version...
Requirement already satisfied: pip in ./venv/lib/python3.13/site-packages (25.2)
Using Python interpreter: /Users/you/projects/mytool/.venv/bin/python3
(venv) $
```

Next time you return to that folder, the same command reactivates the existing venv instantly.

---

## 🛠️ How It Works

- Looks for a `.venv/` directory in the current folder.  
- If missing, runs `python3 -m venv .venv`.  
- Activates via `source .venv/bin/activate`.  
- Prints `which python` for confirmation.

This keeps projects isolated and consistent — without needing to remember venv names.

---

## ❓ Troubleshooting

- **Command not found:**  
  Ensure `/usr/local/bin` (or wherever you placed `venv`) is in your `PATH`.

- **Wrong Python version:**  
  Create your venv with a specific interpreter first, e.g.:

  ```bash
  /usr/bin/python3.12 -m venv .venv && source .venv/bin/activate
  ```

  After that, `source venv` will reuse it automatically.

- **Permission denied:**  
  Re-run the `chmod +x /usr/local/bin/venv` step.

---

## 🧼 Uninstall

To remove the helper:

```bash
sudo rm -f /usr/local/bin/venv
```

(Optional) Remove per-project venvs by deleting their `.venv/` directories.

---

> Made with ❤️ for Python developers who just want to code — not manage environments.

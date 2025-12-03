# HuggingFace Llama 3.1 (8B) - Quick Test

This small repository is used to test calling a HuggingFace-hosted Llama model (meta-llama / Llama 3.1 8B - instruct) from a simple script.


How the script expects credentials
- `test.py` reads the Hugging Face API token from the environment variable `HF_TOKEN`.

Set `HF_TOKEN` (Windows PowerShell)

- Temporary (current PowerShell session only):

	```powershell
	$env:HF_TOKEN = "your_token_here"
	```

- Persistent (user-wide, available in new terminals):

	```powershell
	setx HF_TOKEN "your_token_here"
	# or from PowerShell:
	[Environment]::SetEnvironmentVariable("HF_TOKEN", "your_token_here", "User")
	```

	Note: After `setx` or the PowerShell call you may need to open a new terminal session for the variable to be available.

Use a .env file (optional)
- If you prefer a `.env` file, install python-dotenv and load it from `test.py` before reading the env var:

	```powershell
	pip install python-dotenv
	```

	Create a file named `.env` with:

	```text
	HF_TOKEN=your_token_here
	```

How to run

```powershell
python test.py
```

If `HF_TOKEN` is not set you will see an error when the script tries to read it. Set the token using one of the methods above or update `test.py` to handle the missing token and show a friendly error message.

Next steps (suggested)
- Update `test.py` to check for `HF_TOKEN` and raise a clear RuntimeError with instructions if it is missing.
- Optionally add `.env` loading (python-dotenv) for convenience in local development.

---

Created/edited to record recent inspection and to make it easier to run the test script locally.


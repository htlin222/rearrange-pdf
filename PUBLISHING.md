# Publishing to PyPI

Follow these steps to publish your package to PyPI:

## 1. Create a PyPI account

If you don't already have a PyPI account:
1. Go to https://pypi.org/account/register/
2. Create an account
3. Verify your email

## 2. Create a PyPI API token

1. Log in to PyPI
2. Go to Account Settings → API tokens
3. Create a new API token with scope "Entire account" or limited to this project

## 3. Configure your credentials

Create or edit the file `~/.pypirc`:

```
[pypi]
username = __token__
password = pypi-YOUR-TOKEN-HERE
```

Make sure to set appropriate permissions:
```bash
chmod 600 ~/.pypirc
```

## 4. Upload your package to PyPI

```bash
# Activate your virtual environment
source .venv/bin/activate

# Upload to PyPI
twine upload dist/*
```

## 5. Verify your package

After uploading, check your package page at:
https://pypi.org/project/rearrange-pdf/

## 6. Install your package from PyPI

```bash
pip install rearrange-pdf
```

## 7. For future updates

When you want to release a new version:

1. Update the version number in `setup.py` and `__init__.py`
2. Rebuild the package:
   ```bash
   python -m build
   ```
3. Upload the new version:
   ```bash
   twine upload dist/*
   ```

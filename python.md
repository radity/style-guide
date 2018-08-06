* We usually follow [PEP 8](https://www.python.org/dev/peps/pep-0008/).
* Additionally we follow [Django Coding Style](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/) in our Django projects.

## But..
* We allow up to 119 characters in a line, even if we don't use Django in the project.

## Python module sorter: isort
In PyCharm you can sort imports alphabetically and separate them into sections (CTRL + SHIFT + O in Windows, with a default keymap). If your editor doesn't have the same feature, you can use [isort](https://pypi.org/project/isort/). It's a command line utility, you can install it with **pip**. Please use our isort configuration:

```ini
# ~/isort.cfg
line_length=119
indent='    '
multi_line_output=2
```

## Use pylint instead of flake8
[Pylint](https://pypi.org/project/pylint/) supports **isort**. Many editors support also pylint with an extension. You can disable these warnings:

- E0401
- E1101
- C0103
- C0111
- W0613

Don't forget to set max line length as 119. Example usage:

```bash
$ pylint --disable=E0401,E1101 --max-line-length=119 module.py
```

# Python Style Guide

- We follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) first.
- Then we follow [Django Coding Style](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/) in our Django projects.

## But..

- Allow up to 119 characters in a line, even if we don't use Django in the project.
- Always use **double quote** characters for the [string definition](https://www.python.org/dev/peps/pep-0008/#string-quotes).
- Use **kebab-case** in urls.
- Use **lowerscore_with_underscore_case** in asset file names. (for html, css, javascript and image files.)

## Python module sorter: isort

In PyCharm you can sort imports alphabetically and separate them into sections (CTRL + ALT + O in Windows, with a default keymap). If your editor doesn't have the same feature, you can use [isort](https://pypi.org/project/isort/). It's a command line utility, you can install it with **pip**. Please use our isort configuration:

## Pylint or Flake8

It doesn't matter. Both of them are supporting **isort**.

## Configurations

### setup.cfg

```cfg
[flake8]
max-line-length = 119
ignore = E0401, E1101, C0103, C0111, C0330, W0613

[isort]
line_length = 119
indent = "    "
multi_line_output = 2
```

### .pylintrc
```
[MASTER]
disable=E0401, E1101, C0103, C0111, C0330, W0613

[FORMAT]
expected-line-ending-format=LF
indent-after-paren=4
indent-string='    '
max-line-length=119
```

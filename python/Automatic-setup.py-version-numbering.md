#title: Automatic setup.py version numbering

Problem: Setup.py takes a version number in at least 2 locations (version, and maybe a github release location), and if you import your main package into setup.py you can cause a race condition.  Therefore, the other way to extract the version number is to read it out of your application file python file.

This function, placed at the top of your setup.py file will extract the line that sets the version, containing __version__ = '0.0.0', then executes it and adds it to the namespace.


```python
# setup.py
import os

# Grab line that contains version number from a file,
# then execute it into the name space.
version_line = None

# Open file in package that contains __version__ number
with open(os.path.join('path', 'to', 'file.py')) as f:
    for line in f.readlines():
        if '__version__' in line:
            version_line = line
            break

__version__ = None
if version_line:
    exec(version_line)
else:
    raise ValueError("Version number not found.")
```

```python
#file.py
import x
import y

__version__ = '0.0.1'

def main():
   ...
```

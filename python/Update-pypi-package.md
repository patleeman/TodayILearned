#title: Update pypi package

Update a PyPI package quick and dirty steps necessary.  Based on [This Article](http://peterdowns.com/posts/first-time-with-pypi.html)

1. Increment version number

2. Send release to github:

    ```git
    git tag {version} -m "Add tag for release"
    git tag  # Verify tag is in place
    git push --tags origin master
    ```

3. Ensure .pypirc file is located in ~/ . If not there, follow guide.

4. Send to PyPi live:

    ```bash
    python3 setup.py sdist upload -r pypi
    ```

Note:

Delete tag if there are additional commits to roll into release:

    git tag -d 0.0.1
    git push origin :refs/tags/0.0.1

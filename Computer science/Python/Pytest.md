---
URL: https://realpython.com/pytest-python-testing/
tags:
  - pytest
---
# Fixtures

- Pytest fixtures are functions that can create data, [test doubles][https://en.wikipedia.org/wiki/Test_double], or initialize system state for the test suite. Any test that wants to use a fixture must explicitly use this fixture function as an argument to the test function, so dependencies are always stated up front. 
```python
# fixture_demo.py

import pytest

@pytest.fixture
def example_fixture():
    return 1

def test_with_fixture(example_fixture):
    assert example_fixture == 1
```
### Easy to Filter Tests[](https://realpython.com/pytest-python-testing/#easy-to-filter-tests "Permanent link")

As your test suite grows, you may find that you want to run just a few tests on a feature and save the full suite for later. `pytest` provides a few ways of doing this:

- **Name-based filtering**: You can limit `pytest` to running only those tests whose fully qualified names match a particular expression. **<font style="color:green">You can do this with the `-k` parameter.</font>**
- **Directory scoping**: By default, `pytest` will run only those tests that are in or under the current directory.
- **Test categorization**: `pytest` can include or exclude tests from particular categories that you define.**<font style="color:red"> You can do this with the `-m` parameter.</font>**
# Fixtures: 
- TDD -> [Test-driven development workflow ][https://realpython.com/courses/test-driven-development-pytest/]
- To use fixture `@pytest.fixture`
- Fixture is like to create a variable, which is used for testing many other different function
```python
# test_format_data.py

import pytest

@pytest.fixture
def example_people_data():
    return [
        {
            "given_name": "Alfonsa",
            "family_name": "Ruiz",
            "title": "Senior Software Engineer",
        },
        {
            "given_name": "Sayid",
            "family_name": "Khan",
            "title": "Project Manager",
        },
    ]

def test_format_data_for_display(example_people_data):
    assert format_data_for_display(example_people_data) == [
        "Alfonsa Ruiz: Senior Software Engineer",
        "Sayid Khan: Project Manager",
    ]
```
- So example_people_data is a function, which creates a input, and that has been used for test_format_data_for_displya function
# Pytest plugins
- **Pytest-randomly**: forces your tests to run in a random order
- **pytest-cov**: if you want to measure how well your tests cover your implementation code, the you can use the coverage package.
- **pytest-django**: provides a handful of useful fixtures and marks for dealing with Django test

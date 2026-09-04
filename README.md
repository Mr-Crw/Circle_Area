# Circle_Area

Simple Python code for finding the area of a circle.

## Overview

This repository contains a small, beginner-friendly Python implementation to calculate the area of a circle given its radius. It's intended as an educational example or a minimal utility to reuse in other projects.

## Features

- Compute area using the formula: area = π × r²
- Provides a reusable function and a small CLI script
- Input validation and helpful error messages

## Requirements

- Python 3.7+

## Installation

Clone the repository:

```bash
git clone https://github.com/Mr-Crw/Circle_Area.git
cd Circle_Area
```

No external dependencies are required.

## Usage

Run the script interactively:

```bash
python circle_area.py
```

Or call the function from Python:

```python
from circle_area import area_of_circle

r = 3.0
print(f"Area: {area_of_circle(r)}")
```

Example interactive session:

```
Enter the radius: 3
Area of the circle with radius 3.0 is 28.274333882308138
```

## Example implementation

```python
# circle_area.py
import math


def area_of_circle(radius: float) -> float:
    """Return the area of a circle with the given radius.

    Raises ValueError for negative radii.
    """
    if radius < 0:
        raise ValueError("Radius cannot be negative")
    return math.pi * (radius ** 2)


if __name__ == "__main__":
    try:
        r = float(input("Enter the radius: "))
        print(f"Area of the circle with radius {r} is {area_of_circle(r)}")
    except ValueError:
        print("Please enter a valid non-negative number for the radius.")
```

## Tests

You can add tests with pytest. Example `test_circle_area.py`:

```python
from circle_area import area_of_circle


def test_area_zero():
    assert area_of_circle(0) == 0


def test_area_one():
    import math
    assert area_of_circle(1) == math.pi


def test_negative_radius():
    import pytest
    with pytest.raises(ValueError):
        area_of_circle(-1)
```

Run tests with:

```bash
pip install pytest
pytest
```

## Contributing

Contributions and improvements are welcome. Please open an issue or submit a pull request.

## License

No license is specified. If you want to add one, consider using the MIT License for permissive reuse.

## Contact

Created by Mr-Crw. For questions or suggestions, open an issue or submit a pull request.

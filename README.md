# Package Template

This is a template package for creating function stream functions.

## Testing

The package includes comprehensive pytest tests for the `get_current_time` function.

### Running Tests

#### Option 1: Using Make
```bash
# Run tests
make test

# Run tests with coverage
make test-cov

# Install test dependencies
make install-test-deps
```

#### Option 2: Using pytest directly
```bash
# Install dependencies
pip install -r requirements.txt

# Run tests
python -m pytest test_main.py -v

# Run tests with coverage (requires pytest-cov)
pip install pytest-cov
python -m pytest test_main.py --cov=main --cov-report=term-missing -v
```

### Test Coverage

The test suite covers:

- Default time format behavior
- Custom time format handling
- Empty data dictionary handling
- None data handling
- Various time format patterns (date-only, 12-hour, ISO format)

### Test Structure

- `MockFSContext`: A mock implementation of the FSContext interface
- `TestGetCurrentTime`: Test class containing all test cases
- Each test method follows the Arrange-Act-Assert pattern
- Uses `unittest.mock.patch` to mock datetime for consistent test results

### Adding New Tests

To add new tests:

1. Add new test methods to the `TestGetCurrentTime` class
2. Follow the existing naming convention: `test_<description>`
3. Use descriptive docstrings explaining what each test validates
4. Follow the Arrange-Act-Assert pattern for clear test structure

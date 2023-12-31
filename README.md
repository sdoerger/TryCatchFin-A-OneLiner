<p align="center">
  <a href="https://npmjs.com/package/retonio" target="_blank" rel="noopener noreferrer">
    <img width="400" src="https://ik.imagekit.io/vrfrbvdn0j/sddev/TryCatchFin-A-OneLiner.svg?updatedAt=1696163857267" alt="tryCatchFinFin A OneLiner logo">
  </a>
</p>
<br/>

# TryCatchFin A OneLiner

This repository contains utility functions designed to make try catch and error-handling in Deno applications a tiny notch more easier and more convenient.
Inspired by Go's approach.

## Table of Contents

- [One Line Try Catch and Error](#one-line-try-catch-and-error)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
  - [Usage](#usage)
    - [tryCatchFin](#tryCatchFin)
      - [Example:](#example)
    - [assertError](#asserterror)
      - [Example:](#example-1)
  - [Running Tests](#running-tests)
  - [Contributing](#contributing)
  - [License](#license)

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/your-repo-name.git
```

## Usage

### tryCatchFin

The `tryCatchFin` function provides a way to execute asynchronous operations and neatly handle success and failure cases.

#### Example:

Basic

```typescript
import * as tcUtils from 'https://raw.githubusercontent.com/sdoerger/tryCatchFin-A-OneLiner/main/mod.ts';

const [result, error] = await tcUtils.tryCatchFin(() => 5 + 5);
tcUtils.assertError(error, 'An issue occurred');

console.log(result);
```

Async

```typescript
import * as tcUtils from 'https://raw.githubusercontent.com/sdoerger/tryCatchFinFin-A-OneLiner/main/mod.ts';

async function fetchAnimals() {
    const response = await fetch(
        "https://api.publicapis.org/entries?category=Animals",
        {
            method: "GET",
        }
    );

    return await response.json();
};

const [result, error] = await tcUtils.tryCatchFin(fetchAnimals);
tcUtils.assertError(error, 'An issue occurred');

console.log(result);
```

### assertError

The `assertError` function logs an error message along with the error if it exists.

#### Example:

```typescript
import { assertError } from './helpers.ts';

assertError(new Error("Some error"), "An error occurred");
```

## Running Tests

To run the tests, execute the following command:

```bash
deno test helpers_test.ts
```

## Contributing

Feel free to contribute by submitting pull requests.

## License

MIT License. See `LICENSE` for more information.

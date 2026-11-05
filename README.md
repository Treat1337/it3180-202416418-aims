# AIMS-mini — IT3180 — 202416418

A small Python command-line model of an AIMS DVD shop. The demo builds a cart
with three DVDs and prints each item and the total.

**Repository:** [Treat1337/it3180-202416418-aims](https://github.com/Treat1337/it3180-202416418-aims)

## Requirements

- Python 3.8 or newer
- No third-party packages

## Run

```console
python main.py
```

The demo total is **63.89 USD**.

## Run tests

```console
python -m unittest discover -s tests -v
```

## Features

- DVD model with title, category, director, length, and cost.
- Cart add/remove operations with a 20-item limit.
- Cart total, validated percentage discount, and sorting by title or cost.
- Case-insensitive title and category search.

## Project layout

```text
aims/       Domain model and cart/search operations
tests/      Unit tests
docs/       Lab explanations, use case, and submission status
main.py     Runnable demo
```

See [docs/submission-checklist.md](docs/submission-checklist.md) for the
verified repository, GitHub workflow, review, and LMS status. The documentation
describes Git concepts, but does not claim that PRs, independent review, release
tags, or LMS submission exist when they have not been verified.

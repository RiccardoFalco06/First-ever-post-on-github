# Python Exercises: university exam prep

55 graded Python problems in HackerRank format, plus a small store-management app built as a team exercise. I worked through all of them while preparing for my university Python exam, which I passed with the **highest grade**.

Everything is in a single notebook: [`Hackerrank_exercises.ipynb`](Hackerrank_exercises.ipynb). The newest exercises are at the top.

## Highlight: e-commerce store CLI

The first cell is a menu-driven store manager written by two students, each owning half of the functions (catalog management, then orders and reports):

- product catalog as nested dicts (category → product → price, stock, weight)
- order flow with a **stock check**, **coupon codes** (fixed amount or percentage off) and **shipping rules** (free over €100, by weight otherwise)
- reports: order summary, revenue by category, best-selling products (ranked with a hand-written bubble sort), exportable report

```text
 menu
1. browse products
2. place an order
3. biew reports
4. quit
order placed. subtotal: euro90.00, shipping: euro5, total: euro95.00

  1. order summary
  2. total revenue
  3. popular products
  4. export report
  1. picanha - 3 units sold
```

## What's covered

| Topic | Exercises |
|---|---|
| Basics: I/O, conditionals, math | #1–#13: geometry, quadratic equations, discounts, grade conversion, primes, number patterns |
| Lists and sorting | `linspace`, `merge_lists`, `sort_remove`, `sort_tuples`, `subtract_odd`, `itemsSort`, `uniquify` |
| Strings | `check_anagrams`, `isPangram`, `analyse_text`, `edit_list`, `LetterFilter` (OOP) |
| Dictionaries and counting | `kmer_counting` (DNA k-mers), `common_elements`, `use_dict`, `countDuplicate`, `analyze` |
| Files and CSV | `read_file`, `read_subtitles`, `sort_movies`, `sort_actors` (with `csv`) |
| Algorithms | `balancedSum` (prefix sums, O(n)), `pthFactor`, `maximumPoints`, `maxNutrients` (Gauss sum mod 1e9+7), `closedPaths`, `fourthBit` (bit manipulation), `detect_error` |
| Classes | `LetterFilter` |

A typical solution, `balancedSum`, finds the index where the left and right sums are equal in a single pass:

```python
def balancedSum(arr):
    totale = sum(arr)
    somma_sinistra = 0
    for i in range(len(arr)):
        somma_destra = totale - somma_sinistra - arr[i]
        if somma_destra == somma_sinistra:
            return i
        somma_sinistra += arr[i]
```

Comments are in Italian. Some solutions keep my first attempt commented out next to the final version, so you can follow how my thinking changed.

## Run it

```bash
pip install notebook
jupyter notebook Hackerrank_exercises.ipynb
```

The HackerRank cells read from `stdin` and write to `OUTPUT_PATH`, as the platform's judge expects. To run one locally, call the function directly.

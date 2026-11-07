# Coding conventions

This is an object-oriented analysis package. Reusable logic lives in `dc_optimiser_data/` at the
repository root; notebooks and scripts instantiate its classes and call their methods. When
implementing or changing behaviour, write or update the relevant class first, then call it.

## Source package (`dc_optimiser_data/`)

- **Object-oriented by default.** New logic lives in a class holding state (paths, configs, cached
  frames, fitted models) on `self`. Free functions only for genuinely stateless helpers. Class names
  end in a role noun: `*Loader`, `*Merger`, `*Filter`, `*Calculator`, `*Mapper`, `*Interpolator`,
  `*Fitter`, `*Builder`, `*Visualiser`, `*Exporter`.
- **One class per file**, module name = snake_case of the class (`ModuleTemperatureCalculator` →
  `module_temperature_calculator.py`). Exception: a family of small frozen dataclasses with one
  shared consumer may be grouped in that consumer's module.
- **Re-export from `dc_optimiser_data/__init__.py`.** Add every user-facing class to both the import
  block and `__all__`, so notebooks can `from dc_optimiser_data import <Class>`.
- **CLI scripts are classes too.** `if __name__ == "__main__":` instantiates the class and calls a
  single `run()`. Invoke with `python -m dc_optimiser_data.<module>`.

## Notebooks (`notebooks/`)

**Notebooks call objects; they do not define them.**

- **All imports in the first code cell**, including magics. Never add an import lower down.
- **No `def` / `class` in a notebook cell.** Put it in `dc_optimiser_data/` and import it. Inline
  lambdas in `df.apply(...)`, comprehensions and widget callbacks are fine.
- A cell should read: instantiate → call methods → display.

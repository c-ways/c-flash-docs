# Project architecture

## Global

```bash
├── c_flash_data_analysis
    ├── main function
    │   ├── src
    │       ├── compute_unitary_<function>.py
    │       ├── ...  
    │   └── main.py
    ├── other main function
    │   ├── src
    │       ├── compute_unitary_<function>.py
    │       ├── ...  
    │   └── main.py
```

As package, c-flash-data-analysis contains multiple main functions. Each main functions is independent

The main functions are in `main.py` that calls `compute_unitary.py` from `src/` . In fact the compute unitary allow to compute with multiple group by features.

## Exception

Sometimes a main folder contain multiple main function. For example :

```bash
├── c_flash_data_analysis/
    ├── client_flux/
        ├── client_movement_waterfall/ (main function)
        │   ├── main.py
        │   ├── src/
        │       ├── compute_unitary_<function>.py
        │       ├── ...
        ├── churn_rate/ (main function)
        │   ├── main.py
        │   ├── src/
        │       ├── compute_unitary_<function>.py
        │       ├── ...
```

This archi exception allow main functions that are on the same theme to be grouped.

## Common

A folder `common/` contains function to export workbook excel on multiple perimeter (N, N-1 and N vs N-1). Besides, this folder contains KPI's computation use in most of main functions.
# Churn, retention and recruit rates

## Needs

- transactions N
- transactions N-1
- clients all perimeter

## Goal

One can answer those questions on as many client population that one want:

* What are the churn rate ?
* What are the recruit rates ?
* What are the retain rates ?

By each pivot feature combination, this function will compute :
- Churn/retention/recruit rates and customer number

## Definitions

* **Customer MAINTENU** : Customer active N-1 and N
* **Customer REACTIVE**: Old Customer inactive N-1 but active N
* **Customer ENDORMI**: Customer active N-1 but inactive N
* **Customer INACTIF LONG TERME**: Customer inactive N-1 and inactive N
* **Customer NOUVEAU**: New customer N
* [An active customer](./business-equation.md)

## How to run ?

```python
export_churn_rate(
    transactions_n,
    transactions_n_1,
    clients,
    "outputs/churn-rate-gpby.xlsx",
    cols_to_gpby_params_list=[None, ["classe_age"]],
)
```

In this example, all rates will be computed on `global` and by `classe_age`.

## Workbook expectation

The worbook will have multiple sheets. Each sheets are prefixed with type of computation :
- churn : all rates and customer count

If the computation is on combination of features the sheet will be suffixed with this combination.

## Slide expectation

No slide.

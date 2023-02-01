# First visit basket

## Needs

- transactions N
- transactions N-1
- clients N
- clients N-1

Clients should contain `date_adhesion`

## Goal

One can answer those questions on as many client population that one want :

* What is the financial situation of first shopping basket ?
* What are the financial client behaviors on their first shopping basket ?
* What are the departments most bought for a first basket ?
* Have there been major changes in behaviour vs N-1 ?

By each pivot feature combination, this function will compute :
- Business equation N, N-1 and growth
- Repartition of department on first shopping basket

## Definitions

* **first visit** : The first visit of a customer if he is a new customer during perimeter (when `date_adhesion` is in perimeter)


## How to run ?

```python
export_first_visit_basket(
    transactions_n,
    transactions_n_1,
    clients_n,
    clients_n_1,
    "outputs/first-visit-basket-gpby.xlsx",
    cols_to_gpby_params_list=[None, ["profil_client_canal"]],
)
```

`profil_client_canal` (this feature is computed automatically with `canal`).

## Workbook expectation

The worbook will have multiple sheets. Each sheets are prefixed with type of computation :
- PP eq : business equation of first visit basket
- PP eq growth: growth between N vs N-1
- PP secteur repart: Repartition of department on first visit basket
- PP secteur repart growth: ..

If the computation is on combination of features the sheet will be suffixed with this combination.

## Slide expectation

No slides.
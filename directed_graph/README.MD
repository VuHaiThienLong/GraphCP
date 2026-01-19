## Changelog

### 2026-01-18 to 2026-01-19

* Fixed data leakage issue by preventing embeddings from being computed on the full dataset.
* Updated conformal quantile from nonstandard `1 - alpha` to the correct split conformal quantile using Mondrian (label-conditional) calibration.
* Transitioned from random edge splitting to OGB transductive edge splitting for more realistic evaluation.
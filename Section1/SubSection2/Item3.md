# 1 Setting up a cloud solution environment

## 1.2 Managing billing configuration

### 1.2.3.- Establishing billing budgets and alerts

* Sample Code

```bash
gcloud alpha billing budgets create 
--billing-account=013693-A5FFB7-359B50 
--display-name="Presupuesto A1-976-2021 Proyecto @Sign In 2021" 
--budget-amount=100.75USD 	
--threshold-rule=percent=0.50 
--threshold-rule=percent=0.75,basis=forecasted-spend
```
* *basis:*

    - *forecasted-spend= GASTO PREVISTO*

    - *current-spend = GASTO ACTUAL*

```bash
gcloud alpha billing budgets create --billing-account=013693-A5FFB7-359B50 --display-name="Presupuesto A1-976-2021 Proyecto @Sign 1-97-5" --budget-amount=100.75USD 	--threshold-rule=percent=0.50 --threshold-rule=percent=0.75,basis=forecasted-spend
```

```bash
gcloud alpha billing accounts list
```
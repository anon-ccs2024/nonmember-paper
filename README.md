This repo contains the code and data used for the paper "Towards more accurate and useful data anonymity vulnerability
measures". 

### Data

`BankChurnersNoId_ctgan.json` contains both the original BankChurners data (minus the ID column), and the synthetic data generated by SDV CTGAN. There are three datasets in `BankChurnersNoId_ctgan.json`:
* OriginalTable contains 7088 rows of the original 10127 rows, and is used as the table containing members (after non-members removed). This is used as the training data in the non-member framework.
* TestTable contains 3039 rows of the original, and constitutes the non-members over which predictions are made. This is used as the test data.
* AnonTable contains the synthetic data for CTGAN.

`results.json` contains the data resulting from running `diffTest.py`.

`resultsRecall.json` contains the data resulting from running `diffRecall.py`.

### Code

`diffTest.py` does the actual analysis measures (for both non-member framework and prior framework). It produces `results.json`.

`diffRecall.py` generates the results for generating different recall values by changing the prediction threshold. For categorical attributes only. It produces `resultsRecall.json`.

`displayPerValueResults.py` reads in `results.json` and generates the following plots. Those with accompanying figure number are in the paper.
* `allVsPiiAcc.png` (Figure 4)
* `nonVsPriorAcc.png` (Figure 8)
* `replication.png` (Figure 6)
* `nonVsPriorAcc-nolabel.png `
* `allVsPiiAccNoLab.png`
* `perValue.png`
* `replication-nolabel.png`


`displayRecallResults.py` reads in `resultsRecall.json` and generates the following plots:
* `prec-recall.png` (Figure 5)
* `prec-recall-nolegend.png`

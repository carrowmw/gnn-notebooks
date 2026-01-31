# Test Summary

## Data Summary - Test 1

| Nodes | DL Features | Static Features | Dynamic Features | Agg Features | Raw Features | Edge Features | Edges | Batch Size | Train Batches | Seq Length |
| ----- | ----------- | --------------- | ---------------- | ------------ | ------------ | ------------- | ----- | ---------- | ------------- | ---------- |
| 29    | 21          | 2               | 10               | 9            | 1            | 0             | 812   | 16         | 66            | 12         |

## Data Summary - Test 2

| Nodes | DL Features | Static Features | Dynamic Features | Agg Features | Raw Features | Edge Features | Edges | Batch Size | Train Batches | Seq Length |
| ----- | ----------- | --------------- | ---------------- | ------------ | ------------ | ------------- | ----- | ---------- | ------------- | ---------- |
| 33    | 21          | 13              | 10               | 9            | 1            | 3             | 192   | 32         | 66            | 12         |

## Data Summary - Test 3

| Nodes | DL Features | Static Features | Dynamic Features | Agg Features | Raw Features | Edge Features | Edges | Batch Size | Train Batches | Seq Length |
| ----- | ----------- | --------------- | ---------------- | ------------ | ------------ | ------------- | ----- | ---------- | ------------- | ---------- |
| 33    | 149         | 13              | 22               | 9            | 13           | 3             | 192   | 32         | 66            | 128        |

## Data Summary - Test 4

| Nodes | DL Features | Static Features | Dynamic Features | Agg Features | Raw Features | Edge Features | Edges | Batch Size | Train Batches | Seq Length | Type  |
| ----- | ----------- | --------------- | ---------------- | ------------ | ------------ | ------------- | ----- | ---------- | ------------- | ---------- | ----- |
| 33    | 149         | 13              | 22               | 9            | 13           | 3             | 192   | 32         | 66            | 128        | Train |

## Data Summary - Test 5

| Nodes | DL Features | Static Features | Dynamic Features | Agg Features | Raw Features | Edge Features | Edges | Batch Size | Train Batches | Seq Length | Type  |
| ----- | ----------- | --------------- | ---------------- | ------------ | ------------ | ------------- | ----- | ---------- | ------------- | ---------- | ----- |
| 33    | 149         | 13              | 22               | 9            | 13           | 3             | 192   | 32         | 66            | 128        | Train |
| 33    | 149         | 13              | 22               | 9            | 13           | 3             | 192   | 32         | 66            | 128        | Train |

## Model Summary - Test 1

| Model                | Loss Function | Epochs | Model Params | Train Time | MLP Emb Size | GAT Heads | LR   | Dropout |
| -------------------- | ------------- | ------ | ------------ | ---------- | ------------ | --------- | ---- | ------- |
| MLPMSE               | MSE           | 100    | 7k           | 52.23s     | 64           | N/A       | 1e-4 | 0.1     |
| MLPZINBNLL           | ZINB-NLL      | 100    | 7.9K         | 172.82s    | 64           | N/A       | 1e-4 | 0.1     |
| GATMSE               | MSE           | 40     | 9.7K         | 46.78s     | 16           | 4         | 1e-3 | 0.1     |
| GATZINBNLL           | ZINB-NLL      | 40     | 9.7K         | 85.33s     | 16           | 4         | 1e-3 | 0.1     |
| GATZIPNLL            | ZIP-NLL       | 40     | 9.7K         | 85.33s     | 16           | 4         | 1e-3 | 0.1     |
| GATLSTMZINBLL        | ZINB-NLL      | 100    | 12.1K        | 152.54s    | 16           | 4         | 1e-3 | 0.1     |
| GRUGATBranchZINBNLL  | ZINB-NLL      | 100    | 10.8K        | 130.90s    | 16           | 4         | 1e-3 | 0.1     |
| LSTMGATBranchZINBNLL | ZINB-NLL      | 100    | 11.1K        | 143.12s    | 16           | 4         | 1e-3 | 0.1     |
| LSTMGATSkipZINBNLL   | ZINB-NLL      | 100    | 13.1K        | 146.72s    | 16           | 4         | 1e-3 | 0.1     |
| LSTMGATZINBNLL       | ZINB-NLL      | 100    | 10.1K        | 150.30s    | 16           | 4         | 1e-3 | 0.1     |

## Model Summary - Test 2

| Model         | Loss Function | Epochs | Model Params | Train Time | MLP Emb Size | GAT Heads | LR   | Dropout |
| ------------- | ------------- | ------ | ------------ | ---------- | ------------ | --------- | ---- | ------- |
| MLP           | ZINB-NLL      | 40     | 24.3K        | 1621.13s   | 128          | N/A       | 1e-4 | 0.1     |
| GAT           | ZINB-NLL      | 40     | 24.0K        | 3281.92s   | 32           | 4         | 1e-4 | 0.1     |
| GATZIPNLL     | ZIP-NLL       | 40     | 24.0K        | 2077.80s   | 32           | 4         | 1e-4 | 0.1     |
| GRUGATBranch  | ZINB-NLL      | 40     | 27.7K        | 8928.57s   | 32           | 4         | 1e-4 | 0.1     |
| LSTMGATBranch | ZINB-NLL      | 40     | 28.8K        | 2476.23s   | 32           | 4         | 1e-4 | 0.1     |
| SAGATBranch   | ZINB-NLL      | 40     | 32.6K        | 3957.52s   | 32           | 4         | 1e-4 | 0.1     |

## Performance Summary - Test 1

| Model                | Train ZINB | Train MSE | Test ZINB | Test MSE |
| -------------------- | ---------- | --------- | --------- | -------- |
| MLPMSE               | NA         | 26.01     | NA        | 19.05    |
| MLPZINBNLL           | 2.054      | 25.21     | 2.045     | 18.41    |
| GATMSE               | NA         | 11.74     | NA        | 11.02    |
| GATZINBNLL           | 1.742      | 15.52     | 1.816     | 12.87    |
| GATLSTMZINBLL        | 1.653      | 11.81     | 1.772     | 11.02    |
| GRUGATBranchZINBNLL  | 1.656      | 12.77     | 1.783     | 10.94    |
| LSTMGATBranchZINBNLL | 1.657      | 13.07     | 1.790     | 11.23    |
| LSTMGATSkipZINBNLL   | 1.649      | 12.72     | 1.760     | 10.89    |
| LSTMGATZINBNLL       | 1.650      | 12.21     | 1.754     | 11.00    |

| Model     | Train ZIP | Train MSE | Test ZIP | Test MSE |
| --------- | --------- | --------- | -------- | -------- |
| GATZIPNLL | 1.906     | 13.24     | 2.003    | 11.57    |

## Performance Summary - Test 2

| Model         | Train ZINB | Train MSE | Test ZINB | Test MSE |
| ------------- | ---------- | --------- | --------- | -------- |
| MLP           | 1.614      | 17.61     | 1.574     | 19.31    |
| GAT           | 1.336      | 10.03     | 1.307     | 11.98    |
| GRUGATBranch  | 1.333      | 10.22     | 1.301     | 12.16    |
| LSTMGATBranch | 1.333      | 10.25     | 1.301     | 12.21    |
| SAGATBranch   | 1.335      | 10.30     | 1.304     | 12.34    |

| Model     | Train ZIP | Train MSE | Test ZIP | Test MSE |
| --------- | --------- | --------- | -------- | -------- |
| GATZIPNLL | 1.433     | 8.73      | 1.434    | 10.02    |

## DisenCTR

This is the pytorch implementation for our SIGIR 2022 [paper](https://dl.acm.org/doi/10.1145/3477495.3531851):
> Yifan Wang, Yifang Qin, Fang Sun, Bo Zhang, Xuyang Hou, Ke Hu, 
Jia Cheng, Jun Lei, Ming Zhang (2022). DisenCTR: Dynamic Graph-based Disentangled Representation for Click-Through Rate Prediction

In this paper, we propose we construct a time-evolving user-item interaction graph induced by historical interactions.
And based on the rich dynamics supplied by the graph, we propose a disentangled graph representation module to extract diverse user interests. 

Please cite our paper if you use the code.

### Environment Requirement

The code has been tested running under Python 3.8.13. The required packages are as follows:

- pytorch == 1.11.0 
- torch_geometric == 2.0.4 
- pandas == 1.4.1
- sklearn == 0.23.2

### Running Example

For example, to generate `ML-1M` data for DisenCTR models,
of whitch the raw data has been downloaded and unzipped at `~/raw_data/`.

To process the data, run:
```shell
cd process_data
python process_ML.py
```
which will generate processed data files under the directory `~/Time_data/`.

To conduct experiment on `ML-1M`, run:
```shell
cd ./code
python main.py --data ML --batch 1024 --patience 10 --nConvs 2 --K 4
```
For more execution arguments of DisenCTR, please refer to `~/code/main.py` or run
```shell
python main.py -h
```
Sharding divides a dataset into smaller _shards_.

#### Key Functionalities
1. Each shard is repsonsible for __read/write on its own subset of data__.
2. Each shard needs __less memory__.
3. Each shard can be distributed on smaller nodes, and so the dataset can be __horizontally scaled__.
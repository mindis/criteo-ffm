## Usage

Download and convert the full dataset into CSV format:

```sh
./data.sh
ln -s train.csv tr.csv
ln -s test.csv te.csv
```

Or, use tiny data:

```sh
ln -s train.tiny.csv tr.csv
ln -s test.tiny.csv te.csv
```

Build LIBFFM and preprocess data as the [winning solution did](https://www.csie.ntu.edu.tw/~r01922136/kaggle-2014-criteo.pdf):

```sh
make
```

Note: This repository does not undergo GDBT-based preprocessing stage called `Pre-A` in the document.

Seek the best hyperparams with validation set:

```sh
./ffm-train -k 4 -t 18 -s ${thread_num} -p va.sp tr.sp model
```

Build final model and predict probability for test data:

```sh
./run.sh
```

## References

- [guestwalk/kaggle-2014-criteo](https://github.com/guestwalk/kaggle-2014-criteo)
- [chenhuang-learn/ffm](https://github.com/chenhuang-learn/ffm)
# non-controlflow-hijacking-datasets

## Datasets
There are 21 diffrent datasets dividing into 3 main categories, namely, the *point-of-attack*, *aggregate*, and *time-series* methodology of collecting each exploit. Within in each collection methodology there are five subsets for each exploit (*freak*, *logjam*, *nginx_keyleak*, *nginx_rootdir*, *orzhttpd_restore*, *orzhttpd_rootdir*, *poodle*) consisting of a training set containing only benign behaviour and a testing set containing an even amount of benign and malicious behaviour.

### Example Pseudocode
Here is an example of performing 5-fold cross validation across the different subsets using some Python pseudocode.
```python
for exploit in exploits:
  for i in range(5)
    X_train, Y_train = load_csv('{}/{}/subset_{}/train_set.csv'.format(version, exploit, i)
  
  
    model.train(X_train, Y_train)

    for j in range(5):
      X_test, Y_test = load_csv('{}/{}/subset_{}/test_set.csv'.format(version, exploit, j)
      
      results = model.test(X_test, Y_tes)
```

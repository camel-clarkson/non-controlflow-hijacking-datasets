# non-controlflow-hijacking-datasets


## Introduction
The aim of this readme file is introducing a dataset for utilizing low-level hardware information to detect Non-Control-Flow hijacking attacks. 

Multiple traditional techniques have been proposed to defend computing systems against malware attacks that hijack the control-flow of the victim program (control-oriented attacks). However, non-control-flow hijacking attacks are created in such a way that makes them more difficult to be detected hence prevented with traditional mitigation techniques that target control-oriented attacks. We successfully designed a methodology for the detection of non-control-flow hijacking attacks via employing low-level hardware information formatted as time series. Using architectural and micro-architectural hardware event counts, we model the regular execution behavior of the application(s) of interest, in an effort to detect abnormal execution behavior taking place in the vicinity of the vulnerability. And we organized the experiments recordings as a dataset here in order to encourage the other researchers to push the STA of detection performance. The benefit of this dataset for other ML (machine learning) researchers is that it eliminates the necessity for ML experterts to learn about the domain-specific knowledge of the malware.

We hope this dataset can bridge the discrepancy between the security community and the machine learning community for improving the detection performance of Non-Control-Flow Hijacking Attacks.


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
      
      results = model.test(X_test, Y_test)
```

## Citation
If you are interested in utilizing this dataset for your research. Please cite following paper:

	@inproceedings{torres2019detecting,
	 title={Detecting Non-Control-Flow Hijacking Attacks Using Contextual Execution Information},
	 author={Torres, Gildo and Yang, Zhiliu and Blasingame, Zander and Bruska, James and Liu, Chen},
	 booktitle={Proceedings of the 8th International Workshop on Hardware and Architectural Support for Security and Privacy},
	 pages={1--8},
	 year={2019}
	}



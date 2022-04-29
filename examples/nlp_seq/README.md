## Part-of-Speech Tagging
Trains a simple sequence-based part-of-speech tagger. The following sentence
shows an example.

```
From|ADP the|DT AP|PROPN comes|VBZ this|DT story|NN :|:
```

### Requirements
* Universal Dependency data sets:  https://universaldependencies.org/#download.

    Download via command line: 

    ```
    curl -# -o ud-treebanks-v2.0.tgz https://lindat.mff.cuni.cz/repository/xmlui/bitstream/handle/11234/1-1976/ud-treebanks-v2.0.tgz
    tar xzf ud-treebanks-v2.0.tgz
    ```

### Supported setups
The model should run with other configurations and hardware, but explicitly tested on the following.

| Hardware |  Batch size  | Learning rate | Training time | Accuracy  | TensorBoard.dev |
|:---:|:---:|:---:|:---:|:---:|:---:|
| Nvidia Titan V (12GB) | 64  |  0.05 | 1:36h | 92.5% | [2022-04-29](https://tensorboard.dev/experiment/AuVcQWAGSnqdRMc9kekeog) |

### Running 
```
python train.py --batch_size=64 --model_dir=./ancient_greek \
    --dev=ud-treebanks-v2.0/UD_Ancient_Greek/grc-ud-dev.conllu \
    --train=ud-treebanks-v2.0/UD_Ancient_Greek/grc-ud-train.conllu
```

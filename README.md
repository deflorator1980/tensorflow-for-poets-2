
# Pathology detection in chest X-ray

## Usage (Chest X-rays in forlder radiographs)
```
python3 label_image.py 
```
 or
```
python3 scripts/lable_image.py --image radiographs/1545.jpg 
```

## Train default (depricated)
```
python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=TWO_DS
```

## Train advanced
```
python3 -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --learning_rate=0.001 \
  --how_many_training_steps=5000 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=TWO_DS
```

Library:
https://github.com/googlecodelabs/tensorflow-for-poets-2

Data set:
https://ceb.nlm.nih.gov/repositories/tuberculosis-chest-x-ray-image-data-sets/

To fix "tensorflow:Couldn't understand architecture name '' " 
```
IMAGE_SIZE=224
ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"
```

## Todo
```
https://neurohive.io/ru/tutorial/image-recognition-training-inception-v3/

Try other model, on other params and pictures
```

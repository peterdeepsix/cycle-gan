pip3 install tensorflow-gpu
pip3 install tensorflow-addons
pip3 install --upgrade tb-nightly
pip3 install scikit-image
pip3 install oyaml
pip3 install tqdm

./download_dataset.sh horse2zebra

export CUDA_VISIBLE_DEVICES=0

python3 train.py --dataset horse2zebra

tensorboard --logdir ./output/horse2zebra/summaries --port 6006

export CUDA_VISIBLE_DEVICES=0

python3 test.py --experiment_dir ./output/summer2winter_yosemite

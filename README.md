# MCL

 We released our initial code for MCL, which requires explicit data augmentations.
Getting Started
Dependencies:
python==3.6.13 
pytorch==1.6.0. 
sentence-transformers==2.0.0. 
transformers==4.8.1. 
tensorboardX==2.4.1
pandas==1.1.5
sklearn==0.24.1
numpy==1.19.5
MCL with explicit augmentations
In additional to the original data, SCCL requires a pair of augmented data for each instance.

The data format is (text, text1, text2) where text1 and text2 are the column names of augmented pairs. See our NAACL paper for details about the learning objective.

Step-1. download the original datastes from https://github.com/rashadulrakib/short-text-clustering-enhancement/tree/master/data

step-2. then obtain the augmented data using the code in ./AugData/

step-3 run the code via the following:

python3 main.py \
        --resdir $path-to-store-your-results \
        --use_pretrain SBERT \
        --bert distilbert \
        --datapath $path-to-your-data \
        --dataname searchsnippets_trans_subst_20 \
        --num_classes 8 \
        --text text \
        --label label \
        --objective SCCL \
        --augtype explicit \
        --temperature 0.5 \
        --topk 500 \
        --lr 1e-05 \
        --lr_scale 100 \
        --max_length 32 \
        --batch_size 400 \
        --max_iter 3000 \
        --print_freq 100 \
        --gpuid 0 &


Download the original datastes from https://github.com/rashadulrakib/short-text-clustering-enhancement/tree/master/data


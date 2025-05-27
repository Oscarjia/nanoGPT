#### Set Train Config
nanoGPT/config/train_poem_char.py

#### Prepare data
python3 data/poet_char/prepare.py

#### Train 
python3 train.py config/train_poem_char.py --device=mps --compile=False --eval_iters=20 --log_interval=1 --block_size=64 --batch_size=12 --n_layer=4 --n_head=4 --n_embd=128 --max_iters=2000 --lr_decay_iters=2000 --dropout=0.0

#### Losss

iter 2000: loss 1.6536, time 308.74ms, mfu 0.06%


#### Inference

python3 sample.py --out_dir=out-poem-char --start="MySpring" --num_samples=5 --max_new_tokens=100 --temperature=0.8 --top_k=200 --device=mps

python3 sample.py --out_dir=out-poem-char --start="千问LLM" --num_samples=5 --max_new_tokens=100 --temperature=0.8 --top_k=200 --device=mps
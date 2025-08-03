1. Custom Dataset

```    

    cols = list(df_raw.columns)

    if 'date' in cols:
        cols.remove('date')
    if self.target and self.target in cols:
        cols.remove(self.target)
        df_raw = df_raw[['date'] + cols + [self.target]]
    else:
        df_raw = df_raw[['date'] + cols]

    num_train = int(len(df_raw) * 0.7)
    num_test = int(len(df_raw) * 0.2)
    
    
```

2. acc set
   
single gpu
```
(base) wang_sub@icnl-server:/home/wang/Time-LLM$ cat /home/wang_sub/.cache/huggingface/accelerate/default_config.yaml
compute_environment: LOCAL_MACHINE
debug: false
distributed_type: MULTI_GPU
downcast_bf16: 'no'
gpu_ids: all
machine_rank: 0
main_training_function: main
mixed_precision: fp16
num_machines: 1
num_processes: 1
rdzv_backend: static
same_network: true
tpu_env: []
tpu_use_cluster: false
tpu_use_sudo: false
use_cpu: false
```

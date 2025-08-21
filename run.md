uv init --project .   -p 3.12

uv pip install -r ./docs/chapter2/code/requirements.txt

uv run main.py 

$ uv run docs/chapter2/code/transformer.py 
开始
Error loading tokenizer: (MaxRetryError('HTTPSConnectionPool(host=\'huggingface.co\', port=443): Max retries exceeded with url: /api/models/bert-base-chinese/tree/main/additional_chat_templates?recursive=False&expand=False (Caused by NameResolutionError("<urllib3.connection.HTTPSConnection object at 0x10940aa50>: Failed to resolve \'huggingface.co\' ([Errno 8] nodename nor servname provided, or not known)"))'), '(Request ID: 67210fed-5529-4060-8b83-bf7fdcad84b8)')
Please check your internet connection and try again.


#配置翻墙,再次运行就ok了.

$ uv run docs/chapter2/code/transformer.py
开始
tokenizer.json: 100%|██████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 269k/269k [00:00<00:00, 1.12MB/s]
config.json: 100%|███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 624/624 [00:00<00:00, 8.42MB/s]
number of parameters: 4.55M
idx torch.Size([1, 512])
tok_emb torch.Size([1, 512, 100])
x after wpe: torch.Size([1, 512, 100])
enc_out: torch.Size([1, 512, 100])
x after decoder: torch.Size([1, 512, 100])
tensor([[[-0.6194,  0.1027, -0.0295,  ...,  0.0030, -0.1731,  0.1276]]],
       grad_fn=<UnsafeViewBackward0>)
欒


$ uv run docs/chapter2/code/transformer.py
开始
number of parameters: 4.55M
idx torch.Size([1, 512])
tok_emb torch.Size([1, 512, 100])
x after wpe: torch.Size([1, 512, 100])
enc_out: torch.Size([1, 512, 100])
x after decoder: torch.Size([1, 512, 100])
tensor([[[-0.1506,  0.3414,  0.0067,  ..., -0.1712, -0.1532,  0.0853]]],
       grad_fn=<UnsafeViewBackward0>)
##碩

每次运行结果都不同


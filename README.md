# BTP-Odd-Semester-2024-Team-4

This is a repository for end-to-end process of loading a tokenizer, preparing datasets, fine-tuning pretrained models, translating texts, and evaluating the results using the BhaashikTantraE2EPrototype library.


The notebook provides a comprehensive setup for Google Colab to facilitate the end-to-end workflow for machine translation with BhaashikTantraE2EPrototype. You can copy the above cells into a Jupyter notebook file (`.ipynb`) and run them in Google Colab. Make sure to adapt paths and hyperparameters to your specific requirements!

Before starting with fine-tuning IndicTrans2 models, you will need to restructure the training data in the following format.

```
en-indic-exp
├── train
│   ├── eng_Latn-asm_Beng
│   │   ├── train.eng_Latn
│   │   └── train.asm_Beng
│   ├── eng_Latn-ben_Beng
│   │   └── ...
│   └── {src_lang}-{tgt_lang}
│       ├── train.{src_lang}
│       └── train.{tgt_lang}
└── dev
    ├── eng_Latn-asm_Beng
    │   ├── dev.eng_Latn
    │   └── dev.asm_Beng
    ├── eng_Latn-ben_Beng
    │   └── ...
    └── {src_lang}-{tgt_lang}
        ├── dev.{src_lang}
        └── dev.{tgt_lang}
```

Once you have data ready in above specified format, use the following command.

```bash
bash train_lora.sh <data_dir> <model_name> <output_dir> <direction> <src_lang_list> <tgt_lang_list>
```

We recommend you to refer to `train_lora.sh` for defaults arguments for fine-tuning. Please note that the specified hyperparameters may not be optimal and might require tuning for your use case.

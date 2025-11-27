# How-to-run-xinference-at-b60
How to run xinference at b60

---

## 环境配置
 - 基础环境安装
```bash
conda create -n xinference python=3.10 -y
conda activate xinference
pip install torch==2.8.0 torchvision==0.23.0 torchaudio==2.8.0 --index-url https://download.pytorch.org/whl/xpu
pip install intel-extension-for-pytorch==2.8.10+xpu --extra-index-url https://pytorch-extension.intel.com/release-whl/stable/xpu/us/
pip install oneccl_bind_pt==2.8.0+xpu --index-url https://pytorch-extension.intel.com/release-whl/stable/xpu/us/
````
 - 检查torch安装

```bash
(xinference) root@b60:~# python
Python 3.10.19 (main, Oct 21 2025, 16:43:05) [GCC 11.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> print(torch.version.xpu)
20250101
>>> print(torch.xpu.is_available())
True
>>> print(torch.xpu.get_device_name(0))
Intel(R) Graphics [0xe211
>>>
````
 - 确认安装完成后，安装xinference的相关依赖

```bash
pip install xinference
````

## 启动项目

```bash
xinference-local --host 0.0.0.0 --port 9997
````
<img width="1920" height="1163" alt="image" src="https://github.com/user-attachments/assets/7692666e-77b7-46d4-816e-43da537f270b" />

<img width="1912" height="1094" alt="image" src="https://github.com/user-attachments/assets/cc020201-e6ab-4edf-8a5a-93368b25ecfd" />



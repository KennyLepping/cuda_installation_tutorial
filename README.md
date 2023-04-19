*CUDA Installation Tutorial*

I ran this command from https://pytorch.org/get-started/locally/:
```pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118```

So CUDA 12.1 works with Pytorch, I just don't know how to get that version to work with Pytorch. I would install CUDA 11.8 if you haven't from here:
https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local

Then install NVIDIA cuDNN for CUDA 11.x from here (Local Installer for Windows (Zip):
https://developer.nvidia.com/rdp/cudnn-download (You do have to sign up first)

Then drag the folders from this folder: 
cudnn-windows-x86_64-8.8.1.3_cuda11-archive/

Into this one:
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8

Then CUDA should be enabled. You can check if CUDA is enabled with Python with these commands:

This allows Python code to run in the command line:
```python``` 

You can now check if CUDA is available with Pytorch installed with this code (outputs True if CUDA is enabled or False if it's not):
```import torch; torch.cuda.is_available()```

Exit the Python interactive shell:
```quit()```

If CUDA is still not enabled while using Pytorch and you ran this command from the riffusion GitHub repo page:
```python -m pip install -r requirements.txt```
Then uninstall the Pytorch packages with this command:
```pip uninstall torch torchaudio torchvision```
Then re-install Pytorch with this command:
```pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118```

Then CUDA should be enabled. This is what worked for me with a Nvidia GTX GPU on Windows 10.

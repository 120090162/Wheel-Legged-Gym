```bash
conda create -n wheel-rl python=3.8
conda activate wheel-rl
# make shure your torch+cudn version >= 2.0.1
# this is an example
pip install torch==2.4.1 torchvision==0.19.1 torchaudio==2.4.1 --index-url https://download.pytorch.org/whl/cu124
# install Isaacgym
# problem
# ImportError: libpython3.8.so.1.0: cannot open shared object file: No such file or directory
# solution
# refer to https://blog.csdn.net/sinat_27236401/article/details/148376823

# AttributeError: module 'numpy' has no attribute 'float'
# solution
# the reason is that numpy>1.20, refer to https://forums.developer.nvidia.com/t/attributeerror-module-numpy-has-no-attribute-float/270702 and https://zhuanlan.zhihu.com/p/603611631

# then refer to README to complete the legged gym install

# train
python wheel_legged_gym/scripts/train.py --task=wheel_legged_vmc_flat --headless
# play
python wheel_legged_gym/scripts/play.py --task=wheel_legged_vmc_flat
```
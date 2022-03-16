FROM nvcr.io/nvidia/pytorch:20.11-py3

RUN conda create -n es-clip-code python=3.8 -y
ADD requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt
# RUN pip install torch torchvision
RUN conda install swig -y
RUN pip install 'git+https://github.com/nnaisense/pgpelib.git#egg=pgpelib'
RUN pip install git+https://github.com/openai/CLIP.git
RUN source activate es-clip-code
ADD requirements.all_snapshot.txt /tmp
RUN pip install -r /tmp/requirements.all_snapshot.txt
RUN pip install torch==1.8.1+cu111 torchvision==0.9.1+cu111 torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
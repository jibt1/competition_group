FROM tensorflow/tensorflow:2.3.0-gpu

ENV TRANSFORMERS_CACHE=/workspaces/transformers/cache

COPY ./dependencies/requirements.txt /tmp/pip-tmp/

RUN pip3 install --upgrade pip
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp

RUN pip3 install torch==1.8.1+cpu torchvision==0.9.1+cpu torchaudio==0.8.1 -f https://download.pytorch.org/whl/torch_stable.html
RUN python -m spacy download en_core_web_sm 
RUN python -m spacy download es_core_news_md

EXPOSE 8888
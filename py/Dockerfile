FROM python:3.7

RUN echo $(python3 --version)

RUN useradd -ms /bin/bash lambdaautotraining

WORKDIR /home/lambdaautotraining

RUN apt-get update -y

COPY train.ipynb requirements.txt ./

RUN pip install -r requirements.txt

RUN chown -R lambdaautotraining:lambdaautotraining ./
USER lambdaautotraining

RUN jupyter nbconvert --to script train.ipynb

CMD ["python3","-u","train.py"]

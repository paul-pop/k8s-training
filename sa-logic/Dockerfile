FROM python:3.9

COPY app/requirements.txt .

RUN pip3 install -r requirements.txt

RUN python3 -m textblob.download_corpora

COPY app/sentiment_analysis.py .

EXPOSE 5000

ENTRYPOINT ["python3"]

CMD ["sentiment_analysis.py"]

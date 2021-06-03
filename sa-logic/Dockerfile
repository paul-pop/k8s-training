FROM python:3.9

WORKDIR /app

COPY . .

RUN pip3 install -r requirements.txt

RUN python3 -m textblob.download_corpora

EXPOSE 5000

ENTRYPOINT ["python3"]

CMD ["sentiment_analysis.py"]

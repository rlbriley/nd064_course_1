FROM python:3.8
# Maintainer label is deprecated.
LABEL maintainer="Richard L. Briley Jr."
LABEL version="v1.0.1"
COPY ./techtrends /app
WORKDIR /app
EXPOSE 3111:3111
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 CMD wget http://localhost:3111/healthz
RUN pip install -r requirements.txt
RUN python3 /app/init_db.py
CMD [ "python", "app.py" ]
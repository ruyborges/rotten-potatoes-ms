FROM python:3.10.1-slim

RUN python -m pip install --upgrade pip

WORKDIR /app

COPY ./requirements.txt ./requirements.txt
RUN python -m pip install -r requirements.txt
RUN python -m pip install --upgrade pillow
RUN python -m pip install gunicorn

COPY . .

EXPOSE 5000

ENV FLASK_APP=./app.py
ENV FLASK_ENV=development

CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
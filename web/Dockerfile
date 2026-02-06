FROM python:3.10-slim

RUN useradd -m appuser
WORKDIR /home/appuser/app

COPY requirements.txt

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

RUN chown -R appuser:appuser /home/appuser/app
USER appuser

CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app:]

FROM python:3.12-slim

WORKDIR /usr/src/app

ENV PYTHON_ENV=production

COPY ./requirements.txt /usr/src/app

RUN pip install --cache-dir=/root/.cache/pip -r requirements.txt && \
    rm -rf /root/.cache/pip

RUN groupadd -r engineer && useradd -r -g engineer mehmet

RUN chown -R mehmet:engineer /usr/src/app

USER mehmet

COPY --chown=mehmet:engineer . /usr/src/app

EXPOSE 3000

CMD ["python", "main.py"]
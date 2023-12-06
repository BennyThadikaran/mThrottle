FROM python:3.8.18-slim-bullseye

WORKDIR /app

RUN pip install mthrottle

RUN echo 'from mthrottle import Throttle\n\
t = Throttle({"default": {"rps": 3}}, 10)\n\
for i in range(10):\n\t\
print(i)\n\t\
t.check()\n\
print("All working well")' > test.py

COPY mthrottle/ mthrottle/
COPY __init__.py .

CMD ["python3", "test.py"]

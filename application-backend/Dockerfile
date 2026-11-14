FROM python:3.12-slim
WORKDIR /app

# Built from repository root (Cloud Build default)
COPY application-backend/requirements.lock application-backend/pyproject.toml ./
RUN pip install --no-cache-dir -r requirements.lock

COPY application-backend/src/ ./src/
COPY application-backend/schema/ ./schema/
COPY contracts/ /contracts/

ENV APP_ENV=production APP_HOST=0.0.0.0 APP_PORT=8080 CONTRACTS_DIR=/contracts
EXPOSE 8080
CMD ["python", "-m", "lingualive_api"]

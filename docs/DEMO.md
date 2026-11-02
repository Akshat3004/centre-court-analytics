# Local demo and validation

**This portfolio repository does not contain executable source code.** Run all commands in the [original team's repository](https://github.com/vishaljha2121/big_data_spring_proj).

## Local demo

Prerequisites: Python, Node.js/npm and original project data/model artifacts.

```bash
git clone https://github.com/vishaljha2121/big_data_spring_proj.git
cd big_data_spring_proj
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
bash scripts/run_full_demo.sh
```

The team runbook reports the following local addresses: React dashboard `http://127.0.0.1:5173`, FastAPI docs `http://127.0.0.1:8000/docs`, API health `http://127.0.0.1:8000/health`. Stop with `bash scripts/stop_full_demo.sh`.

## Optional Kafka/Spark replay

Requires Docker, Java and a compatible Spark/Kafka connector environment.

```bash
docker compose -f infra/docker/docker-compose.kafka.yml up -d
bash infra/kafka/kafka_setup.sh
bash scripts/run_streaming_demo.sh --max-events 1000
```

## Validation in original repository

```bash
.venv/bin/python scripts/final_preflight_check.py
.venv/bin/python scripts/smoke_test_full_demo.py
.venv/bin/python scripts/validate_api_contract.py
.venv/bin/python scripts/validate_frontend_build.py
.venv/bin/python -m pytest tests
```

Documentation: [team demo runbook](https://github.com/vishaljha2121/big_data_spring_proj/blob/main/docs/final_demo_runbook.md).

**Visuals:** capture real dashboard, match browser, replay and model-performance screenshots from a successful local run; do not pass off identical placeholder images as separate pages.

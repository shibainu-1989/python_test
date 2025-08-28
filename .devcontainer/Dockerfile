FROM python:3.11-slim

# 最低限のツール
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential git && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /work

# ← これがポイント：.devcontainer 内に置いた requirements.txt をコピー
COPY requirements.txt /work/requirements.txt

# 依存をインストール（唯一の真実源は requirements.txt）
RUN pip install --no-cache-dir -U pip && \
    pip install --no-cache-dir -r /work/requirements.txt

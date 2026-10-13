# food-security-agent

A food security analyst assistant that helps analysts understand why food insecurity is changing in a region, built for the AI Engineering Buildcamp capstone.

## The Problem

Humanitarian analysts, researchers, and development practitioners need to explain why food insecurity is changing in a region. Today that means reading through multiple situation reports, separately checking conflict event data and rainfall trends, and piecing the picture together by hand. It's slow, and it's easy to miss a source or overstate a link between unrelated signals.

## What It Does

An analyst asks a question like "What is driving food insecurity in Bay region this season, and have conflict events or rainfall changed there?" The system retrieves relevant passages from food security reports, calls tools to pull recent conflict events and rainfall anomalies for that region and period, and returns a cited answer.

It separates what the sources state from what the data merely correlates with, and says clearly when evidence is thin, stale, or missing. It will never present a causal claim the data can't support.

The first version is built and tested on Somalia, chosen for its rich public data on both conflict and climate, but country is a parameter in the retrieval and tools, so the same system can be adapted to other countries by pointing it at different reports and regions.

## Setup

1. Install uv if you don't have it yet: https://docs.astral.sh/uv/getting-started/installation/

2. Clone this repository (or download the zip and extract it).

3. Create a `.env` file from the template and add your API key:

       cp .env.example .env

4. Install dependencies:

       uv sync

5. Start Jupyter:

       uv run jupyter notebook

## Notebooks

- `notebooks/01-setup.ipynb` - smoke test that confirms your environment works
- `notebooks/02-rag.ipynb` - a minimal RAG baseline you can adapt to your own data

## Data

Put your project data in the `data/` folder. See `notebooks/02-rag.ipynb` for how to load it.

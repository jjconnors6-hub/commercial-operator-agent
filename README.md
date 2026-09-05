# Commercial Operator Agent

AI agent that turns public-source research into a commercial brief.

## What it does

Provide a company URL and the agent researches:

- business and ownership context
- products and portfolio
- customers and customer patterns
- competition and status quo
- ICP and priority-account characteristics
- buying group
- commercial motion
- pricing, economics, and value
- expansion paths
- commercial organization
- open questions and commercial gaps
- messaging reframe

The output is a meeting-ready commercial brief designed to support deeper GTM analysis and operator judgment.

## Inputs

- Company URL
- Optional research context / objective
- Optional product or business-unit focus
- Optional buyer / persona focus

## Output

A public-source commercial brief with inline sourcing, customer evidence, market context, commercial analysis, and a concise bottom-line read.

## Example

The app includes an Elevate Healthcare example so the finished output can be reviewed without running a live search.

## Run locally

Install dependencies:

`py -m pip install -r requirements.txt`

Run the app:

`py -m streamlit run app.py`

The app expects `OPENAI_API_KEY` to be configured through Streamlit secrets or the environment.

## Notes

- Uses public internet sources and OpenAI web search.
- Research quality depends on the amount and quality of public information available.
- Public evidence is separated from inference internally so unsupported claims are not presented as facts.
- The brief is designed as the first step in commercial analysis, before deeper GTM recommendations and execution planning.

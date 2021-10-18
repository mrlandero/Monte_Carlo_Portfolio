# Monte_Carlo_Portfolio
A financial planner for retirement. This tool will forecast the performance of their retirement portfolio in 30 years. To do this, the tool will make an Alpaca API call via the Alpaca SDK to get historical price data for use in Monte Carlo simulations.

----------

## Technologies
This project leverages python 3.7 with the following packages:

**[Operating System Library](https://docs.python.org/3/library/os.html)** - For being able to work with our operating system.<br>
**[Requests Library](https://pypi.org/project/requests/)** - For making requests to our APIs<br>
**[JSON Library](https://www.json.org/json-en.html)** - For creating comprehensible data structures from our API responses.<br>
**[Pandas Library](https://pandas.pydata.org/)** - For use of financial functions for calculations.<br>
**[Dotenv Library](https://pypi.org/project/python-dotenv/)** - For being able to work with our .env files.<br>
**[Alpaca Trade API](https://alpaca.markets/docs/)** - For retrieving historical pricing data for our stocks.<br>
**[Monte Carlo Simulation Library](https://umn.bootcampcontent.com/SVivanco/valhalla/blob/491913853a10bb86a912f102ef3fb26746a2e6ec/code/MCForecastTools.py)** - For running Monte Carlo Simulations for our portfolio.<br>
**[Matplot Library](https://matplotlib.org/)** - For being able to plot our calculated data.

----------

## Installation Guide

Before running the application first import the following dependencies:

```python
import os
import requests
import json
import pandas as pd
from dotenv import load_dotenv
import alpaca_trade_api as tradeapi
from MCForecastTools import MCSimulation

%matplotlib inline
```

Make sure the "requests library" & the "JSON library" are included in your conda dev environment.

```python
conda list requests

conda list json
```
The result on your screen should resemble the following image:

![Requests/JSON Verification](requests_json_image.png)

If your development environment is missing either package, you can directly install it.

To install the Requests library, check that your development environment is active, and then run the following command:

```python
conda install -c anaconda requests
```

To install the JSON library, check that your development environment is active, and then run the following command:

```python
conda install -c jmcmurray json
```

With the python-dotenv library, you can read key-value pairs from an environment file (.env) and add them as environment variables.

To install this library, run the following command in your terminal:

```python
pip install python-dotenv
```

Install the Alpaca SDK
Alpaca is an API for stock trading. With the Alpaca SDK, you can interact with the Alpaca API.

To install this SDK, run the following command in your terminal:

```python
pip install alpaca-trade-api
```

Verify the Installations
To verify that the library and SDK installations completed, call the pip list function together with the grep -E argument, which enables plain-text searches via the command line. The following code shows this function call:

```python
pip list | grep -E "python-dotenv|alpaca-trade-api"
```

The following image shows the results in your terminal:

![Alpaca Installation Verification](alpaca_verification.png)

Alternatively, you can call the conda list function twice, first with the library name and then with the SDK name, as the following code shows:

```python
conda list python-dotenv

conda list alpaca-trade-api
```

The following image shows the results in your terminal:

![Alpaca Installation Verification](alpaca_two_verification.png)

Get the API Keys
To use certain APIs, you need API keys. You use these unique identifiers to establish an authenticated, secure connection to an API. You'll get keys for both the Quandl and Alpaca APIs.

Get the Quandl API Key
To get your API key, you need to sign up for a Quandl account. Go to the Quandl homepage (Links to an external site.), and then click Sign Up (which appears on the main menu along the top of the page). The following image shows the Quandl homepage:

![Quandal Home Page](quandl_home_page.png)

On the “Step 1 of 3” sign-up page that appears, enter your first and last names, and then select Personal as your purpose for using Quandl. Click Next to move to the next page. The following image shows the “Step 1 of 3” page:

![Quandl Signup Page 1](quandl_page_one.png)

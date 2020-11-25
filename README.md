[![PyPI](https://img.shields.io/pypi/v/crypto_empyrical?color=%234ec726&style=flat-square)](https://pypi.org/project/empyrical/)

# crypto_empyrical

crypto_empyrical is a fork of Quantopian's Empyrical package modified by [Jesse](https://jesse.trade) to work for 24/7 markets of cryptocurrency. 

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Support](#support)
- [Contributing](#contributing)
- [Testing](#testing)

## Installation
```
pip install crypto_empyrical
```

## Usage

Simple Statistics
```python
import numpy as np
from crypto_empyrical import max_drawdown, alpha_beta

returns = np.array([.01, .02, .03, -.4, -.06, -.02])
benchmark_returns = np.array([.02, .02, .03, -.35, -.05, -.01])

# calculate the max drawdown
max_drawdown(returns)

# calculate alpha and beta
alpha, beta = alpha_beta(returns, benchmark_returns)

```

Rolling Measures
```python
import numpy as np
from crypto_empyrical import roll_max_drawdown

returns = np.array([.01, .02, .03, -.4, -.06, -.02])

# calculate the rolling max drawdown
roll_max_drawdown(returns, window=3)

```

Pandas Support
```python
import pandas as pd
from crypto_empyrical import roll_up_capture, capture

returns = pd.Series([.01, .02, .03, -.4, -.06, -.02])

# calculate a capture ratio
capture(returns)

# calculate capture for up markets on a rolling 60 day basis
roll_up_capture(returns, window=60)
```

## Testing
- install requirements
  - "nose>=1.3.7",
  - "parameterized>=0.6.1"

```
./runtests.py
```

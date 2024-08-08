# Chapter 8: Survival Analysis
## Overview of Survival Analysis
Survival analysis is a branch of statistics that deals with analyzing the expected duration until one or more events happen, such as death in biological organisms and failure in mechanical systems. This type of analysis is used extensively in medical research, engineering, and social sciences.

## Kaplan-Meier Estimator
The Kaplan-Meier estimator is a non-parametric statistic used to estimate the survival function from lifetime data.

### Example: Kaplan-Meier Estimator
Let's use a hypothetical dataset to demonstrate the Kaplan-Meier estimator.

```python
import pandas as pd
import numpy as np
from lifelines import Kaplan-MeierFitter
import matplotlib.pyplot as plt

# Example dataset
data = {
    'Time': [5, 6, 6, 2, 4, 4, 5, 8, 2, 3],
    'Event': [1, 0, 1, 1, 0, 1, 1, 0, 1, 1]
}
df = pd.DataFrame(data)

# Kaplan-Meier estimator
kmf = Kaplan-MeierFitter()
kmf.fit(durations=df['Time'], event_observed=df['Event'])

# Plotting the survival function
kmf.plot_survival_function()
plt.title('Kaplan-Meier Estimate of Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()
```

## Cox Proportional Hazards Model
The Cox Proportional Hazards model is a semiparametric model used to investigate the association between the survival time of patients and one or more predictor variables.

### Example: Cox Proportional Hazards Model
```python
from lifelines import CoxPHFitter

# Example dataset
data = {
    'Time': [5, 6, 6, 2, 4, 4, 5, 8, 2, 3],
    'Event': [1, 0, 1, 1, 0, 1, 1, 0, 1, 1],
    'Age': [50, 60, 65, 45, 50, 55, 70, 65, 40, 55],
    'Treatment': [1, 1, 0, 1, 0, 0, 1, 0, 1, 1]
}
df = pd.DataFrame(data)

# Cox Proportional Hazards model
cph = CoxPHFitter()
cph.fit(df, duration_col='Time', event_col='Event')

# Summary of the model
print(cph.summary)

# Plotting the survival function
cph.plot()
plt.title('Cox Proportional Hazards Model')
plt.show()
```

## Parametric Survival Models
Parametric survival models assume that the survival times follow a specific statistical distribution. Common choices include exponential, Weibull, and log-normal distributions.

### Example: Parametric Survival Model (Weibull)
```python
from lifelines import WeibullFitter

# Example dataset
data = {
    'Time': [5, 6, 6, 2, 4, 4, 5, 8, 2, 3],
    'Event': [1, 0, 1, 1, 0, 1, 1, 0, 1, 1]
}
df = pd.DataFrame(data)

# Weibull model
wf = WeibullFitter()
wf.fit(df['Time'], df['Event'])

# Plotting the survival function
wf.plot_survival_function()
plt.title('Weibull Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()

# Summary of the model
print(wf.summary)
```

### Example: Parametric Survival Model (Exponential)
```python
from lifelines import ExponentialFitter

# Example dataset
data = {
    'Time': [5, 6, 6, 2, 4, 4, 5, 8, 2, 3],
    'Event': [1, 0, 1, 1, 0, 1, 1, 0, 1, 1]
}
df = pd.DataFrame(data)

# Exponential model
ef = ExponentialFitter()
ef.fit(df['Time'], df['Event'])

# Plotting the survival function
ef.plot_survival_function()
plt.title('Exponential Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()

# Summary of the model
print(ef.summary)
```

## Example: Complete Workflow
Here is a complete example that demonstrates Kaplan-Meier estimator, Cox Proportional Hazards model, and parametric survival models.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from lifelines import Kaplan-MeierFitter, CoxPHFitter, WeibullFitter, ExponentialFitter

# Example dataset
data = {
    'Time': [5, 6, 6, 2, 4, 4, 5, 8, 2, 3],
    'Event': [1, 0, 1, 1, 0, 1, 1, 0, 1, 1],
    'Age': [50, 60, 65, 45, 50, 55, 70, 65, 40, 55],
    'Treatment': [1, 1, 0, 1, 0, 0, 1, 0, 1, 1]
}
df = pd.DataFrame(data)

# Kaplan-Meier estimator
kmf = Kaplan-MeierFitter()
kmf.fit(durations=df['Time'], event_observed=df['Event'])
kmf.plot_survival_function()
plt.title('Kaplan-Meier Estimate of Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()

# Cox Proportional Hazards model
cph = CoxPHFitter()
cph.fit(df, duration_col='Time', event_col='Event')
print("Cox Proportional Hazards Model Summary:")
print(cph.summary)
cph.plot()
plt.title('Cox Proportional Hazards Model')
plt.show()

# Weibull model
wf = WeibullFitter()
wf.fit(df['Time'], df['Event'])
wf.plot_survival_function()
plt.title('Weibull Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()
print("Weibull Model Summary:")
print(wf.summary)

# Exponential model
ef = ExponentialFitter()
ef.fit(df['Time'], df['Event'])
ef.plot_survival_function()
plt.title('Exponential Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()
print("Exponential Model Summary:")
print(ef.summary)
```

In this chapter, we covered the basics of survival analysis, including the Kaplan-Meier estimator, Cox Proportional Hazards model, and parametric survival models. We provided examples to demonstrate how to perform these analyses using Python's lifelines library and how to interpret the results.

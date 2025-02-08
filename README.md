# FiGuy

# Skills Used

- Python

## Development Notes

### [Python Virtual Environment](https://docs.python.org/3/library/venv.html)

1. Create new virtual environment

   python -m venv name_of_environment

_Note: You do NOT want to push env changes to your repo!! You can create a new one whenever necessary, treat it like the node_modules folder_

2. Activate Virtual Environment:

   - Windows: `.\finance_env\Scripts\activate`
   - Mac/Linus: `source finance_env/bin/activate`

3. Verify Activation

   - Windows: `where python`
   - Mac/Linux: `which python`

   **ISSUE:** `where python` command did NOT product an output in my terminal
   **STEPS OF CORRECTION:** _Commands run in terminal_

   1. Verify `\finance_env\Scripts` is listed in the path
      Run `echo $env:PATH`
      _Should show all PATH locations_
   2. Verify there is a version of python within the Scripts folder
      Run `.\finance_env\Scripts\python --version`
      _Should show current version being used for your project_
   3. Verify if Scripts path is listed at base level
      Run `C:\Windows\System32\where.exe python`
      _Will show all instances of python, want Scripts path to appear_

4. Verify VSCode Integrations
   - Press: Ctrl + Shift + P
   - Enter: "Python Select Interpreter"
   - Choose `finance_env` as interpreter
     _NOTE: This allows VSCode to remain in sync with the libraries and packages in the venv_
     _i.e. will give you an error if you try to use any libraries not installed in the venv_
5. To Deactivate Venv
   Run `deactivate`

### Amending Git Commit

If user wants to correct/change something done in a previous commit w/o creating a new commit or reverting old commit run `git commit --amend` and then `git push -f`
_The `push -f` is necessary since you are telling git to change the history of the latest commit NOT just adding a change_

### Packages

- [numpy](https://numpy.org/doc/stable/user/absolute_beginners.html): allows you to do mathematical equations quickly
- [pandas](https://pandas.pydata.org/getting_started.html): creates data tables (similar to excel data sheets)
- [matplotlib](https://matplotlib.org/stable/users/explain/quick_start.html): graphing or visualization of data
- yfinance: pulls financial data
- mplfinance and plotly: used for data visualization
- jupyter
  _NOTE: `requirements.txt` required if anticipating to share with user_
  - Create file based on your installations: `pip freeze > requirements.txt` or manually add the exact versions of each package you are using
  - When others want to install packages: `pip install -r requirements.txt`

#### Essential Libraries for Data Science: pandas, numpy, matplotlib

##### Create a DataFrame with pandas

`df = pandas.DataFrame(data)` => returns a df that configures corresponding values to maintain the same value types/format (i.e. values=[10, 5, 2.37] => df values=[10.00, 5.00, 2.37])

##### Functions with numpy as np

`np.array([2, 4, 6])`=> creates array of values (required to be of the same type)
`np.mean(data)`
`np.sum(data)`
`np.min(data)`
`np.max(data)`
`np.median(data)`
`np.random.seed(42)` => adding a random seed will ensure reproducibility, generate the same random numbers with each run
_NOTE: if you want truly random numbers that can't be actively reproduced don't add seed_
`np.random.normal()` => normal distribution of random numbers ([learn more](https://hyperskill.org/university/numpy/numpy-normal-distribution))
`np.std(data)` => This finds the standard deviation of the data array

- Standard Deviation = sqrt(variance)
- Variance = sum(( value - avg )^2)

##### Create plot with matplotlib as plt

`plt.figure(figsize=(8,4))` => defines the figure itself and its corresponding size (h,w)
`plt.plot(dataPts, marker="o", linestyle="-.", color="blue")` => this tells the values to be used on y-axis and styles the line chart
`plt.title("Figure Title Here")`
`plt.xlabel("X-axis label here")`
`plt.ylabel("Y-axis label here")`
`plt.grid(True)` => do you want the grid lines to show or just the line chart
`plt.show()` => prints the plot you created on screen

### Random Walk Model

a mathematical model that describes how a variable moves randomly and without a clear pattern

- [A Random Walk Down Wall Street by Burton G. Malkeil](https://www.google.com/books/edition/A_Random_Walk_Down_Wall_Street/Avu090CNzb8C?hl=en&gbpv=1&pg=PA13&printsec=frontcover)

_Stocks are a cumilitive sum of passed stock prices (i.e. the price today depends on the price yesterday)_

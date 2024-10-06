# Alan Author Strikes Again: More on Confirming Conjunctions of Disconfirmed Hypotheses

The Alan Author Effect is a surprising phenomenon in Bayesian Confirmation Theory. It occurs when a piece of evidence confirms the conjunction of two hypotheses but at the same time disconfirms each hypothesis individually, more formally:

1. $P(H_1\land H_2|E)>P(H_1\land H_2)$
1. $P(H_1|E)<P(H_1)$ and $P(H_2|E)<P(H_2)$

Surprisingly, there is a new and prima facie stronger
version of this effect where additionally, the evidence confirms the conjunction of the negated hypotheses:

3. $P(\neg H_1\land \neg H_2|E)>P(\neg H_1\land \neg H_2)$

And perhaps even more surprisingly, this seemingly stronger effect and the original effect are actually *coextensional*.

This repo examines how likely the two effects are to occur with the help of Monte Carlo simulation methods.

The results are published in Analysis:
 - https://academic.oup.com/analysis/advance-article-abstract/doi/10.1093/analys/anad103/7731114

A penultimate version of the paper can be found here:

- https://github.com/jottemka/alan_author_effect/blob/main/anad103.pdf

## Results

Two types of prevalence values are calculated:

1. *Conjunctive Prevalence*:
    - For the Original Alan Author Effect: proportion of probability functions satisfying conditions 1 and 2.
    - For the Strong Alan Author Effect: proportion of probability functions satisfying conditions 1, 2 and 3.

    Since both effects are coextensional, this value must be identical for the Original Alan Author Effect and the Strong Alan Author Effect. 

1. *Conditional Prevalence*:
    - For the Original Alan Author Effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying condition 2.
    - For the Strong Alan Author Effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying conditions 2 and 3.

The results are shown in the table below:

</style>
<table id="T_386cd">
  <thead>
    <tr>
      <th id="T_386cd_level0_col0" class="col_heading level0 col0" >Effect</th>
      <th id="T_386cd_level0_col1" class="col_heading level0 col1" >Conjunctive Prevalence</th>
      <th id="T_386cd_level0_col2" class="col_heading level0 col2" >Conditional Prevalence</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td id="T_386cd_row0_col0" class="data row0 col0" >Alan Author Effect</td>
      <td id="T_386cd_row0_col1" class="data row0 col1" >0.025006</td>
      <td id="T_386cd_row0_col2" class="data row0 col2" >0.100333</td>
    </tr>
    <tr>
      <td id="T_386cd_row1_col0" class="data row1 col0" >Strong Alan Author Effect</td>
      <td id="T_386cd_row1_col1" class="data row1 col1" >0.025006</td>
      <td id="T_386cd_row1_col2" class="data row1 col2" >0.111471</td>
    </tr>
  </tbody>
</table>

For comparison, the conjunctive prevalence of instances of Simpson's paradox is around 0.0083, the conditional prevalence is around .0333. So, the Alan Author Effect is more prevalent.

## Further Reading

1. https://conservancy.umn.edu/server/api/core/bitstreams/659aa39b-5cd4-46d3-8f9a-94e97fafe464/content

1. https://www.cambridge.org/core/journals/philosophy-of-science/article/abs/how-to-confirm-the-conjunction-of-disconfirmed-hypotheses/45E5ECA1BA4293F465BEC18677CBD4BC

## Virtual Environment Setup

Use the requirements file to create a new environment for this task. 

```Bash
pyenv local 3.11.3
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

### **`WindowsOS`** type the following commands :

Install the virtual environment and the required packages by following commands.

For `PowerShell` CLI :

```PowerShell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
```

For `Git-Bash` CLI:

```
python -m venv .venv
source .venv/Scripts/activate
pip install --upgrade pip
pip install -r requirements.txt
```

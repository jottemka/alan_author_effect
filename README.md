# Alan Author Strikes Again: More on Confirming Conjunctions of Disconfirmed Hypotheses

The Alan Author Effect is a surprising phenomenon in Bayesian Confirmation Theory. It occurs when a piece of evidence E confirms the conjunction of two hypotheses H1∧H2 but at the same time disconfirms each hypothesis H1 and H2 individually, more formally:

1. $P(H_1\land H_2|E)>P(H_1\land H_2)$
1. $P(H_1|E)<P(H_1)$ and $P(H_2|E)<P(H_2)$

Interestingly, there is a new and seemingly stronger version of this effect where additionally, E confirms that *both* hypotheses are *false*:

3. $P(\neg H_1\land \neg H_2|E)>P(\neg H_1\land \neg H_2)$

And even more interestingly, this seemingly stronger effect and the original effect are *coextensional*. This means that the Strong Alan Author Effect occurs if and only if the Original Alan Author Effect occurs.

This repo examines how likely the two versions of the Alan Author Effect are to occur with the help of Monte Carlo simulation methods. It also compares them to instances of Simpson's Paradox.

The results are published in Analysis:
 - https://academic.oup.com/analysis/advance-article-abstract/doi/10.1093/analys/anad103/7731114

A penultimate version of the paper can be found here:

- https://github.com/jottemka/alan_author_effect/blob/main/anad103.pdf

## Results

Two types of prevalence values are calculated:

1. *Conjunctive Prevalence*:
    - For the Original Alan Author Effect: proportion of probability functions satisfying conditions 1 and 2.
    - For the Strong Alan Author Effect: proportion of probability functions satisfying conditions 1, 2 and 3.

1. *Conditional Prevalence*:
    - For the Original Alan Author Effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying condition 2.
    - For the Strong Alan Author Effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying conditions 2 and 3.

Since the Original Alan Author Effect and the Strong Alan Author Effect are coextensional, their conjunctive prevalence must be identical. For comparison, the prevalence of instances of Simpson's Paradox are also provided. The results are shown in the table below:

<table id="T_74a50">
  <thead>
    <tr>
      <th id="T_74a50_level0_col0" class="col_heading level0 col0" >Effect</th>
      <th id="T_74a50_level0_col1" class="col_heading level0 col1" >Conjunctive Prevalence</th>
      <th id="T_74a50_level0_col2" class="col_heading level0 col2" >Conditional Prevalence</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td id="T_74a50_row0_col0" class="data row0 col0" >Alan Author Effect</td>
      <td id="T_74a50_row0_col1" class="data row0 col1" >0.025101</td>
      <td id="T_74a50_row0_col2" class="data row0 col2" >0.100429</td>
    </tr>
    <tr>
      <td id="T_74a50_row1_col0" class="data row1 col0" >Strong Alan Author Effect</td>
      <td id="T_74a50_row1_col1" class="data row1 col1" >0.025101</td>
      <td id="T_74a50_row1_col2" class="data row1 col2" >0.111581</td>
    </tr>
    <tr>
      <td id="T_74a50_row2_col0" class="data row2 col0" >Simpson's Paradox</td>
      <td id="T_74a50_row2_col1" class="data row2 col1" >0.008324</td>
      <td id="T_74a50_row2_col2" class="data row2 col2" >0.033288</td>
    </tr>
  </tbody>
</table>

The investigated instances of Simpson's Paradox are cases where the following conditions are jointly satisfied:

4. $P(H\land E|X)>P(H|X)P(E|X)$
4. $P(H\land E|\neg X)>P(H|\neg X)P(E|\neg X)$
4. $P(H\land E)\ngtr P(H)P(E)$

The above results show that even though the Alan Author Effect not very prevalent, it is more likely to occur than instances of Simpson's Paradox.

## Further Reading

1. http://fitelson.org/confirmation/carnap_logical_foundations_of_probability.pdf

1. https://conservancy.umn.edu/server/api/core/bitstreams/659aa39b-5cd4-46d3-8f9a-94e97fafe464/content

1. https://www.tandfonline.com/doi/abs/10.1080/01621459.1972.10482387

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

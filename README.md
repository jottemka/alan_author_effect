# Alan Author Strikes Again: More on Confirming Conjunctions of Disconfirmed Hypotheses

The Alan Author Effect is a surprising phenomenon in Bayesian Confirmation Theory. It occurs when a piece of evidence confirms the conjunction of two hypotheses but at the same time disconfirms each hypothesis individually. The effect received its name from the paper *How to Confirm the Conjunction of Disconfirmed Hypotheses* by David Atkinson, Jeanne Peijnenburg and Theo Kuipers:

> Alan Author has just made an important discovery. From
  his calculations it follows that recent evidence $E$ supports the conjunction of two popular hypotheses, $H_1$ and $H_2$ . With great gusto he sets himself to the writing of a research proposal in which he explains his idea and asks for time and money to work out all its far-reaching consequences. Alan Author’s proposal is sent to Rachel Reviewer, who—to his dismay— writes a devastating report. Ms. Reviewer first recalls what is common knowledge within the scientific community, namely that $E$ strongly disconfirms not only $H_1$, but also $H_2$ as well. Then she intimates that Alan Author is clearly not familiar with the relevant literature; for if he were,  he would have realized that any calculation that results in confirming the conjunction of two disconfirmed hypotheses must contain a mistake. At any rate, he should never have launched this preposterous idea, which  will make him the laughing stock of his peers. Is Reviewer right? Did Author indeed make a blunder by assuming that $E$ might confirm a conjunction of hypotheses, $H_1\land H_2$, given that the same $E$ disconfirms $H_1$ and $H_2$ separately?

The surprising answer is that that Rachel Reviewer is wrong. The following two conditions are consistent:

1. $P(H_1\land H_2|E)>P(H_1\land H_2)$
1. $P(H_1|E)<P(H_1)$ and $P(H_2|E)<P(H_2)$

And they are even consistent with the following seemingly stronger condition:

3. $P(\neg H_1\land \neg H_2|E)>P(\neg H_1\land \neg H_2)$

This repo examines how prevalent the original and the stronger version of the effect are with the help of Monte Carlo simulation methods.

The results are published in Analysis:
 - https://academic.oup.com/analysis/advance-article-abstract/doi/10.1093/analys/anad103/7731114

A penultimate version of the paper can be found here:

- https://github.com/jottemka/alan_author_effect/blob/main/anad103.pdf

## Results

Two types of prevalence values are calculated:

1. *Conjunctive Prevalence*:
    - Original effect: proportion of probability functions satisfying conditions 1 and 2.
    - Strong effect: proportion of probability functions satisfying conditions 1, 2 and 3.

1. *Conditional Prevalence*:
    - Original effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying condition 2.
    -  Strong effect: proportion of probability functions satisfying conditions 1 *among* the probability functions satisfying conditions 2 and 3.

The results are shown in the table below:

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

Since the original and the strong effect are coextensional, their conjunctive prevalence must be identical. For comparison, the prevalence of instances of Simpson's Paradox is also provided, i.e. cases where the following conditions are jointly satisfied:

4. $P(H\land E|X)>P(H|X)P(E|X)$
4. $P(H\land E|\neg X)>P(H|\neg X)P(E|\neg X)$
4. $P(H\land E)\ngtr P(H)P(E)$

The above results show that even though the Alan Author Effect not very prevalent, it is more prevalent than instances of Simpson's Paradox.

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

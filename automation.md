This document presents two methods of making a 'career table' more automatically:
- a few-shot prompt for ChatGPT 3.5
- Python lists and pandas

## Use GenAI to create your table.
Here is a few-shot prompt you can use to create a markdown table. I have tested it on ChatGPT 3.5 and 4.
Both work.

To use the prompt, enter your passions, interests and goals into the final incomplete example, and then
submit it to ChatGPT. 

```
Following the below examples, I want you to output (as a codeblock) a markdown 
table. Each section (Passions, Interests, etc) should be represented as a 
column in the markdown table.

$$$ INPUT
Passions:
Making a difference
Continuous learning

Interests:
Machine Learning
Open Source Contribution

3 Months:
Complete Machine Learning Course
First Open Source Contribution

6 Months:
Launch a personal project
Speak at a local tech meetup

1 Year:
Mentor a junior developer
Publish a technical blog

2 Years:
Lead a development team

5 Years:
Found a tech startup

$$$ OUTPUT
```markdown
| Passions | Interests | 3 Months | 6 Months | 1 Year | 2 Years | 5 Years |
|:--------------------|:---------------------------|:--------------------------------|:----------------------------|:--------------------------|:---------------------|:------------------|
| Making a difference | Machine Learning | Complete Machine Learning Course| Launch a personal project | Mentor a junior developer | Lead a development team | Found a tech startup |
| Continuous learning | Open Source Contribution | First Open Source Contribution | Speak at a local tech meetup| Publish a technical blog | | |

$$$ INPUT
Passions:
Environmental activism
Renewable energy

Interests:
Solar power technology
Environmental policy

3 Months:
Volunteer for a beach cleanup
Start a local awareness campaign

6 Months:
Install a solar panel at home
Join a policy advocacy group

1 Year:
Organize a regional conference

2 Years:
Implement a community renewable energy project

5 Years:
Influence national environmental policy

$$$ OUTPUT
| Passions | Interests | 3 Months | 6 Months | 1 Year | 2 Years | 5 Years |
|:-----------------------|:--------------------------|:---------------------------------|:-----------------------------|:---------------------------------|:----------------------------------------|:--------------------------------|
| Environmental activism | Solar power technology | Volunteer for a beach cleanup | Install a solar panel at home | Organize a regional conference | Implement a community renewable energy project | Influence national environmental policy |
| Renewable energy | Environmental policy | Start a local awareness campaign | Join a policy advocacy group | | | |


$$$ INPUT
Passions:
Art and design
Cultural heritage
Interests:
Photography
Travel blogging

3 Months:
Start a photography blog
Visit a new country

6 Months:
Host a photography exhibition
Write a travel guide

1 Year:
Collaborate with a museum

2 Years:
Publish a book on cultural travels

5 Years:
Establish a foundation for art and culture preservation

$$$ OUTPUT
| Passions | Interests | 3 Months | 6 Months | 1 Year | 2 Years | 5 Years |
|:----------------------|:----------------|:--------------------------|:---------------------------|:----------------------------|:---------------------------------|:---------------------------------------------|
| Art and design | Photography | Start a photography blog | Host a photography exhibition | Collaborate with a museum | Publish a book on cultural travels | Establish a foundation for art and culture preservation |
| Cultural heritage | Travel blogging | Visit a new country | Write a travel guide | | | |

$$$ INPUT
Passions:
Helping people flourish
Learning things deeply

Interests:
Generative AI
CPython

3 Months:
AWS Associate Architect
Published to PIP
Start a Holberton AWS Cloud Guild

6 Months:
AWS Associate Developer
Attended 20 meetups

1 Year: 
AWS Associate Data Engineer

2 Years:
AWS Speciality 

5 Years:
Contribute to CPython

$$$ OUTPUT
| Passions   | Interests   | 3 Months   | 6 Months   | 1 Year   |   2 Years | 5 Years   |
|:-----------|:------------|:-----------|:-----------|:---------|----------:|:----------|
| Helping people flourish         |  Generative AI          |   AWS Associate Architect      |    AWS Associate Developer     |     AWS Associate Data Engineer   |  AWS Speciality      |     Contribute to CPython    |
| Learning things deeply        |  CPython       |   Published to PIP         |    Attended 20 Meetups        |      |         |        |
|         |          |   Start a Holberton AWS Cloud Guild       |       |      |        |       |
|            |             |            |            |          |         |           |

$$$ INPUT
Passions:
?

Interests:
?

3 Months:
?

6 Months:
?

1 Year: 
?

2 Years:
?

5 Years:
?

$$$ OUTPUT
```

## Use Python lists and pandas
You will need to pip install pandas and tabulate.
### Setup
```shell
$ pip install pandas
...
$ pip install tabulate
...
```

### The Python code
```python
""" 
If you prefill the category lists (passions, interests, etc), this module will print out the information 
you provide as a markdown table when executed as a module.
"""

import pandas as pd
from typing import List, Dict

# Fill these lists with your data.
passions: List[str] = [
    'example1'
    'example2'
]

interests: List[str] = [
    'example3'
    'example4',
    'example5'
    'example6'
]

three_months: List[str] = [
    'example7'
    'example8'
]

six_months: List[str] = [
    'example9'
    'example10'
]
one_year: List[str] = [
    'example11'
    'example12'
]
two_years: List[str] = [
    'example13'
    'example14'
]
five_years: List[str] = [
    'example15'
    'example16',
    'example17',
    'longer example18',
]

data: Dict[str, List[str]] = {
    'Passions': passions,
    'Interests': interests,
    '3 Months': three_months,
    '6 Months': six_months,
    '1 Year': one_year,
    '2 Years': two_years,
    '5 Years': five_years,
}


def print_career_table(data: Dict[str, List[str]]) -> None:
    """Print a (markdown) career table from the given dictionary of lists."""

    df = create_df(data)
    markdown = df.to_markdown(index=False)
    print(markdown)


def create_df(data: Dict[str, List[str]]) -> pd.DataFrame:
    """Create a dataframe from lists of potentially differing lengths."""

    max_column_length = max([len(data[key]) for key in data])
    for key in data:
        while len(data[key]) < max_column_length:
            data[key].append('')
    return pd.DataFrame(data)


if __name__ == "__main__":
    print_career_table(data)

```



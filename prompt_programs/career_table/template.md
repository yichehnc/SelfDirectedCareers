## Create a markdown table by using labelled lists as the individual columns

Here is a few-shot prompt you can use to create a markdown table. I have tested it on ChatGPT 3.5 and 4.
Both work.

To use the prompt, enter your passions, interests and goals into the final incomplete example.
This is the customisable component of the prompt template. Once you have completed the template, submit it to ChatGPT. 

### Prompt Template

```markdown
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

# Tinytroupe-Project-2
# TinyTroupe Simulation: Analyst & CFO Earnings Discussion

## Library Imports

```python
from tinytroupe.environment import TinyWorld
from tinytroupe.agent import TinyPerson
```

## Simulation on an analyst speaking with a CFO on earnings report

### Persona #1: Analyst

```python
analyst = TinyPerson("Andrew")
analyst.define("age", 34)
analyst.define("nationality", "American")
analyst.define("occupation", "Equity Research Analyst at a major investment firm")
analyst.define("professional_history", "Andrew has covered the tech sector for over 8 years, focusing on quarterly earnings and long-term valuation models.")
```

### Persona #2: CFO

```python
cfo = TinyPerson("Alex")
cfo.define("age", 52)
cfo.define("nationality", "Canadian")
cfo.define("occupation", "Chief Financial Officer of a Fortune 500 tech company")
cfo.define("professional_history", "Alex has over 25 years in corporate finance and has led two IPOs. Focused on transparency and investor confidence.")
```

---

## Initiate Conversation

```python
world = TinyWorld("Office",[analyst, cfo])
world.make_everyone_accessible()

analyst.listen("Thanks for joining todays meeting, Can you give us an overview of this quarter’s performance?")
```

## Run Simulation

```python
world.run(3)
```

---

## Sample Output

```
USER --> Andrew: [CONVERSATION] 
          > Thanks for joining todays meeting, Can you give us an overview of this quarter’s
          > performance?
TinyPerson(name='Andrew')

>>> world.run(3)

Andrew acts: [THINK] 
            > I need to prepare an overview of this quarter's performance for the meeting. I should
            > focus on key metrics and any significant changes compared to previous quarters.
Andrew acts: [TALK] 
            > Sure! This quarter, we've seen a 15% increase in revenue compared to the last quarter,
            > driven mainly by strong sales in our tech sector. However, expenses have also risen by
            > 10%, which has impacted our overall profit margins. I can provide more detailed
            > insights if needed.
Andrew acts: [THINK] 
            > I should be ready to answer any follow-up questions about the performance metrics or
            > provide more details if requested. It's important to be thorough and clear in my
            > explanations.
Andrew acts: [DONE] 

Andrew --> Alex: [CONVERSATION] 
            > Sure! This quarter, we've seen a 15% increase in revenue compared to the last quarter,
            > driven mainly by strong sales in our tech sector. However, expenses have also risen by
            > 10%, which has impacted our overall profit margins. I can provide more detailed
            > insights if needed.

Alex acts: [THINK] 
          > Andrew mentioned a 15% increase in revenue, which is great news. However, the 10% rise
          > in expenses is concerning and could affect our profit margins. I need to consider how we
          > can manage expenses better while maintaining sales growth.
Alex acts: [TALK] 
          > Thanks for the update, Andrew. It's encouraging to see the revenue growth, but we need
          > to address the rising expenses. Can you provide more details on which areas the expenses
          > have increased?
Alex acts: [DONE] 

Alex --> Andrew: [CONVERSATION] 
          > Thanks for the update, Andrew. It's encouraging to see the revenue growth, but we need
          > to address the rising expenses. Can you provide more details on which areas the expenses
          > have increased?
─────────────────────────────────────────────────────────── Office step 2 of 3 ────────────────────────────────────────────────────────────

Andrew acts: [THINK] 
            > I need to analyze the areas where expenses have increased. I should focus on specific
            > departments or categories that contributed to the rise in costs, such as operational
            > expenses, marketing, or R&D.
Andrew acts: [TALK] 
            > Certainly, Alex. The increase in expenses is primarily due to higher operational
            > costs, which have risen by about 8%. This includes increased staffing costs and some
            > unexpected maintenance expenses. Additionally, our marketing budget has expanded by 5%
            > to support new product launches. Would you like more details on any specific area?
Andrew acts: [THINK] 
            > I should be prepared for any further questions from Alex or the team regarding the
            > expenses. It's important to have a clear understanding of the reasons behind the
            > increases and how we can manage them moving forward.
Andrew acts: [DONE] 

Andrew --> Alex: [CONVERSATION] 
            > Certainly, Alex. The increase in expenses is primarily due to higher operational
            > costs, which have risen by about 8%. This includes increased staffing costs and some
            > unexpected maintenance expenses. Additionally, our marketing budget has expanded by 5%
            > to support new product launches. Would you like more details on any specific area?

Alex acts: [THINK] 
          > The increase in operational costs by 8% is significant, especially with staffing and
          > maintenance expenses. The 5% increase in the marketing budget for new product launches
          > is understandable, but we need to evaluate if it's yielding the expected results. I
          > should consider how we can optimize these costs moving forward.
```

---

## Question #1

To install the tinytroupe package, you will need to create a code space on the cloud in your GitHub repository and then type:

```bash
git clone https://github.com/microsoft/TinyTroupe.git
cd TinyTroupe/
pip install .
```

Export your OpenAI API key:

```bash
export OPENAI_API_KEY="000000"
```

Enter the Python environment:

```bash
python
```

Then import the following packages:

```python
from tinytroupe.environment import TinyWorld
from tinytroupe.agent import TinyPerson
```

Then you are ready to create personas and run your own simulations.

---

## Question #2: What is the Turing Test for LLMs?

The Turing Test for LLMs is a test that is used to see whether or not a machine can imitate a human conversation and on the other end, can it fool a human into thinking they are talking with another human. Similar to how well trained ChatGPT is, when you ask it questions and it gives you insightful responses with a ton of information, it's hard to tell that you're *not* speaking with a help desk agent at times.

### Some of the key criteria for passing this test are:

- **Fluency**: Responses must be grammatically correct, natural, and human-like.  
- **Contextual understanding**: AI must stay on topic and remember parts of the conversation.  
- **Emotional realism**: Should simulate emotions believably if appropriate.  
- **Plausible beliefs and opinions**: Even if fake, they should make sense and be consistent.  
- **Avoidance of obvious tells**: Should not say things like “As an AI model…” or use unnatural phrases.  
- **Handling ambiguity**: Can clarify or interpret unclear questions like a human would.  
- **Improvise like a human**: If asked something unexpected, can make something up believably.

---

## Question #3: Does My Simulation Pass the Turing Test?

I think my simulation passes the Turing Test. Although short due to API limitations, the two personas were set to be in an office in a conversation between the analyst and CFO of a company. Quarterly earnings were discussed where the analyst gave specific business drivers in an insightful way and even demonstrated professionalism and did not appear to be “robotic”. Numerical figures were given and a concise answer was given as if they were a human.

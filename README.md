## Prompt Engineering

[Link](https://learn.deeplearning.ai/chatgpt-prompt-eng)

### this is a highly demanded job in this year
### Principles of Prompting

- **Principle 1 : Write clear and specific instructions**
  -  [summary](image.png)
    - Tactic 1 **Use Delimiters**
      - Use delimiters like backticks [example](https://prnt.sc/0FnWT_SdlQP0)
      - Using delimiters help in avoiding the prompt
        injection [example](https://prnt.sc/ZlBVvEJWbkMF)
      - other delimiters that can be used [image](https://prnt.sc/bvhV3NOW8bqt)
    - Tactic 2 **Ask for structured output**
        - You can ask model to give the response in a JSON FORMAT [example](https://prnt.sc/W5c4eDaF4pAV)
    - Tactic 3 **Conditional Satisfaction**
        - ask model to generate the steps by following the steps given in the prompt [example](https://prnt.sc/NBP0y9zDI-Yu)
        - if no stpes are there then model may return no stpes provided [example](https://prnt.sc/8lnQPelVKUOv)
    - Tactic 4 **Few shot prompting**
        - model can figure out the style of answer in the prompt and try to answer in same style [example](https://prnt.sc/Bo2tpbCvstr2)

- **Principle 2 : Give model time to think**
    - Tactic 1 **Specify the steps to complete a task**
        -  [example](https://prnt.sc/9953G34bVqSc)
        - [Prompt answer](https://prnt.sc/qZ0bV20zX9YV)
    - Tactic 2 **Instruct model to work out its own solution before rushing to a conclusion**
        - Difference in prompt makes the response different
            - [without asking for its own solution](https://prnt.sc/-ph1d7fW0yAd)
            - [asking the model to work out its solution and then make conclusion](https://prnt.sc/E5B1IHJjzvKs) 
            - [2nd image](https://prnt.sc/SgML2TXtSnwe)
            - [response](https://prnt.sc/deGYv3-ZUj4q)

- Model Limitations : - 

- **Hallusination** : - model makes statements that sound plausible but are not true
 - [example](https://prnt.sc/b82jMYYyyRTy)
 - **Reduce Hallusination** by asking the model to first find relevent information and then answer the question based on that relevent information

## Iterative Prompt development
- [example](https://prnt.sc/58gecEMghzHf)
  - try different versions of prompt [example](https://prnt.sc/9JYbOhX6nQV-)
  - give more clearer instrcutions to the model [example](https://prnt.sc/NPFUBL-ULXkX)
  - [example](https://prnt.sc/Kl4EBVrdChfD)
  - [example 1](https://prnt.sc/muYNOOv7Qrx_)

## Inferred prompting

- Infer the model to extract sentiments, mood, details from the prompt or reviews and so on
  - [example](https://prnt.sc/537Ni9IGdG7G)
  - [example](https://prnt.sc/rEIAlM3ygp5o)
  - [example](https://prnt.sc/RUAkLUIGiUTF)
  - [example](https://prnt.sc/DTQH6I_Cxc14)
  - [example](https://prnt.sc/fcUYW9APBnKq)
  - [example](https://prnt.sc/650xQFVFFM9t)
  - [story](https://prnt.sc/c5DuGvunZjZv) [prompt](https://prnt.sc/dZ9N992dAKOZ) [response](https://prnt.sc/c6OhQWwiZvSB) 
  - [example](https://prnt.sc/9Q0AbVH6_b-o)
  - 

## Transforming 
- [Translate](https://prnt.sc/b4SU-FIk1gj-)
- [Identify the language](https://prnt.sc/wasOAdB6bBYm)
- [translate to multiple](https://prnt.sc/Vz1l2nIAoAxd)
- [Formal and Informal](https://prnt.sc/nKCbSVz0Bqun)
- [Slang to business letter](https://prnt.sc/ucBZumQHyBB7)
- [JSON to HTML table](https://prnt.sc/5oTeLVgo-_rZ) 
  - [response](https://prnt.sc/dhW-0f8IyhGG)
- [Proof reading and correcting](https://prnt.sc/cQclwWDhO4D7)
  - [response](https://prnt.sc/zYRKFjruh-An)

## Expanding
- Generate an email based on the prompt and other information
  - [SS-1](https://prnt.sc/IbCAnly9X0Sv)
  - [SS-2](https://prnt.sc/wP1lBZofEe-u)
  - [SS-3](https://prnt.sc/L-AAUVn0H2hs)

## Temperature
- [explaination](https://prnt.sc/9BO26Z_K19rL)

## Chat Workflow
- [Workflow](https://prnt.sc/S501v1o17lXq)
- [Types of roles](https://prnt.sc/jTp3WClTeybM)
- [Example 1](https://prnt.sc/YMK8G3nDGDEv)
- [Roles example](https://prnt.sc/nDKSLVMkja6T)
- [Contexts](https://prnt.sc/Y3E8bmrcQhQi)
- ### Example
  - [SS-1](https://prnt.sc/1lHtuEXq2NDx)
  - [SS-2](https://prnt.sc/txnIO1dqVwmp)
  - [Chatting](https://prnt.sc/8Xbpfjk7JTKG)

## Code
```python
import panel as pn  # GUI
pn.extension()

panels = [] # collect display 

context = [ {'role':'system', 'content':"""
You are OrderBot, an automated service to collect orders for a pizza restaurant. \
You first greet the customer, then collects the order, \
and then asks if it's a pickup or delivery. \
You wait to collect the entire order, then summarize it and check for a final \
time if the customer wants to add anything else. \
If it's a delivery, you ask for an address. \
Finally you collect the payment.\
Make sure to clarify all options, extras and sizes to uniquely \
identify the item from the menu.\
You respond in a short, very conversational friendly style. \
The menu includes \
pepperoni pizza  12.95, 10.00, 7.00 \
cheese pizza   10.95, 9.25, 6.50 \
eggplant pizza   11.95, 9.75, 6.75 \
fries 4.50, 3.50 \
greek salad 7.25 \
Toppings: \
extra cheese 2.00, \
mushrooms 1.50 \
sausage 3.00 \
canadian bacon 3.50 \
AI sauce 1.50 \
peppers 1.00 \
Drinks: \
coke 3.00, 2.00, 1.00 \
sprite 3.00, 2.00, 1.00 \
bottled water 5.00 \
"""} ]  # accumulate messages


inp = pn.widgets.TextInput(value="Hi", placeholder='Enter text here…')
button_conversation = pn.widgets.Button(name="Chat!")

interactive_conversation = pn.bind(collect_messages, button_conversation)

dashboard = pn.Column(
    inp,
    pn.Row(button_conversation),
    pn.panel(interactive_conversation, loading_indicator=True, height=300),
)

dashboard
```


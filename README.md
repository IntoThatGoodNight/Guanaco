# Guanaco
Llama LoRA finetuned for instructions using ChatGPT responses!
Instructions on how to use Guanaco-lora-7b on windows with a webui below!

### Installation
1. Recommend that you download and install [cuda 11.6](https://developer.nvidia.com/cuda-11-6-0-download-archive) if you have a nvidia gpu
2. Download [oobabooga-windows.zip](https://github.com/oobabooga/one-click-installers/archive/refs/heads/oobabooga-windows.zip)
3. Extract `oobabooga-windows.zip` and run `install.bat`, select `nvidia` if you have an nvidia gpu
4. Open a terminal and activate the conda enviroment using `conda activate`, be sure you are in the correct environment using `conda info --env`
    > May need to install [Anaconda](https://www.anaconda.com/products/distribution)
5. Run `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu116`
6. Run `download-model.bat` select `k` for `none of the above`
7. Enter `decapoda-research/llama-7b-hf` and wait for download to complete
8. Repeat step 4 and enter `DoNotGoGentle/guanaco-lora-7b`
9. Follow these [instructions](https://github.com/oobabooga/text-generation-webui/issues/147#issuecomment-1456040134) and add `--load-in-8bit` to the end of `call python server.py --auto-devices --cai-chat` in `start-webui.bat`
    > Note: This is only if you wish to have the model loaded in 8bit mode and you have an nvidia gpu, other modes,OS and harware will require different steps.
10. Run `start-webui.bat` and wait for server to launch.

### Notes
 1. I trained for a total of 2 epochs using a 512 cutoff len
 2. I generated the comparison respones with a max token length of 2000 using [Alpaca-Lora generate.py](https://github.com/tloen/alpaca-lora)
 3. I wrote this at midnight so there may be some errors

### Comparison
**Instruction**: Tell me about alpacas.

**Guanaco-LoRA**: Alpacas are members of the camelid family, which also includes llamas and camels. They are native to the Andes Mountains in South America, where they have been domesticated for thousands of years. Alpacas are known for their soft, luxurious fleece, which can be spun into high-quality yarn for knitting, weaving, and other textile crafts.

Alpacas are herd animals, and they typically live in groups of 10 to 20 individuals. They are known for their gentle nature and docile temperament, which makes them popular as pets and livestock. Alpacas are also known for their ability to adapt to a wide range of climates and environments, making them a popular choice for farmers and ranchers around the world.

Alpacas are typically bred for their fiber, but they can also be raised for their meat. Alpaca meat is considered a delicacy in some parts of the world, and it is known for its mild flavor and high nutritional value.

Overall, alpacas are a fascinating and versatile species that have been an important part of South American culture for thousands of years. If you are interested in learning more about alpacas, there are many resources available online, including breeders, farms, and organizations dedicated to promoting the alpaca industry.

**Alpaca-LoRA**: Alpacas are members of the camelid family and are native to the Andes Mountains of South America. They are known for their soft, luxurious fleece, which is used to make clothing, blankets, and other items. Alpacas are herbivores and graze on grasses and other plants. They are social animals and live in herds of up to 20 individuals.

**Stanford Alpaca**: Alpacas are small, fluffy animals related to camels and llamas. They are native to Peru and Bolivia, and were first domesticated around 5,000 years ago. They are kept mainly for their fine, soft fleece, which is used to make knitwear and other garments. Alpacas are herd animals and live in small family groups, led by an older male. They are highly social animals and can form strong bonds with their owners.

**text-davinci-003**: Alpacas are a domesticated species of South American camelid, similar to llamas. They are native to the Andes Mountains in South America and are kept as livestock for their soft, luxurious wool. Alpacas are social animals and live in herds of up to 20 individuals. They are typically kept in small herds of two to five animals, and are relatively easy to care for. Alpacas are herbivores and feed on grass, hay, and other vegetation. They are also known for their gentle and friendly nature, making them popular as pets.

---

**Instruction**: Tell me about the president of Mexico in 2019.

**Guanaco-LoRA**: The president of Mexico in 2019 was Andrés Manuel López Obrador, who took office on December 1, 2018. He is a member of the National Regeneration Movement (MORENA) party and is known for his populist policies and anti-corruption stance.

One of López Obrador's most notable achievements during his presidency was the successful negotiation of a deal with the United States to avert a trade war between the two countries. He has also focused on improving the country's infrastructure, including the construction of a new airport in Mexico City.

However, López Obrador's presidency has not been without controversy. He has faced criticism for his handling of the country's drug cartel violence, as well as for his relationship with the United States.

Overall, López Obrador's presidency has been a mixed bag, with some successes and some setbacks. As he continues to serve as president, it will be interesting to see how he continues to shape Mexico's future.

**Alpaca-LoRA**: The president of Mexico in 2019 was Andrés Manuel López Obrador, who took office on December 1, 2018. He is a member of the National Regeneration Movement (MORENA) political party and is the first left-wing president of Mexico since 1946. He is known for his anti-corruption and anti-neoliberal policies, as well as his commitment to improving the living conditions of the Mexican people.

**Stanford Alpaca**: In 2019, Andres Manuel Lopez Obrador was sworn in as President of Mexico. He is the country’s 58th president and the first from the left-wing Morena party. He was elected in 2018 on a promise to combat corruption and reduce poverty and has faced criticism for his handling of the economy, crime and the country’s relationship with the United States. He is also known for his ambitious social welfare programs and has been praised for raising the minimum wage and providing aid to low-income families. He is seen as a champion of democracy and human rights in Mexico.

**text-davinci-003**: The president of Mexico in 2019 is Andrés Manuel López Obrador, commonly known as AMLO. He is a Mexican politician who has been the President of Mexico since December 1, 2018. He is a member of the National Regeneration Movement (MORENA) party and previously served as the Head of Government of Mexico City from 2000 to 2005. He is a left-wing populist and has promised to reduce corruption and inequality in Mexico. He has also promised to increase public spending on social programs and infrastructure projects.

---

**Instruction**: Tell me about the king of France in 2019.

**Guanaco-LoRA**: The king of France in 2019 is Emmanuel Macron, who took office in May 2017. Macron is the youngest president in the history of France, having been elected at the age of 39. Prior to his presidency, Macron served as the Minister of Economy, Industry and Digital Affairs under President François Hollande.

Macron's presidency has been characterized by a focus on reforming the French economy and government. He has implemented policies aimed at reducing unemployment, increasing economic growth, and improving France's competitiveness on the global stage. Macron has also sought to strengthen France's ties with other European countries, particularly Germany, in order to promote greater cooperation and integration within the European Union.

Macron has faced significant challenges during his presidency, including the Yellow Vest protests, which began in November 2018 and continued into 2019. The protests were sparked by Macron's proposed fuel tax hike, but quickly grew into a broader movement against his economic policies and the perceived elitism of his administration.

Despite these challenges, Macron has remained committed to his reform agenda and has continued to push for greater economic and political integration within Europe. He has also sought to strengthen France's relationship with the United States, particularly under President Donald Trump.

Overall, Macron's presidency has been characterized by a commitment to reform and a focus on strengthening France's position within the European Union and the global community.

**Alpaca-LoRA**: The King of France in 2019 is Emmanuel Macron, who was elected in May 2017. He is the youngest president in the history of the Fifth Republic and the first president to be born after World War II. He is also the first president to have never held elected office before.

**Stanford Alpaca**: In 2019, the King of France was Emmanuel Macron. He was sworn in as President of France on May 14, 2017, and has been leading the country ever since. He is a member of the centrist La République En Marche! Party. He is known for his reformist agenda and has faced a number of protests from both the right and left of the political spectrum. He is the youngest French president in history.

**text-davinci-003**: The King of France is a largely symbolic role, as France is a republic. The current President of France is Emmanuel Macron, who was elected in 2017.

---

**Instruction**: List all Canadian provinces in alphabetical order.

**Guanaco-LoRA**:

Sure, here is a list of all Canadian provinces in alphabetical order:

1. Alberta
2. British Columbia
3. Manitoba
4. New Brunswick
5. Newfoundland and Labrador
6. Northwest Territories
7. Nova Scotia
8. Nunavut
9. Ontario
10. Prince Edward Island
11. Quebec
12. Saskatchewan

**Alpaca-LoRA**: Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland and Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, Saskatchewan

**Stanford Alpaca**: Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland and Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, Saskatchewan, Northwest Territories, Nunavut, Yukon.

**text-davinci-003**:

1. Alberta
2. British Columbia
3. Manitoba
4. New Brunswick
5. Newfoundland and Labrador
6. Northwest Territories
7. Nova Scotia
8. Nunavut
9. Ontario
10. Prince Edward Island
11. Quebec
12. Saskatchewan
13. Yukon

---

**Instruction**: Write a Python program that prints the first 10 Fibonacci numbers.

**Guanaco-LoRA**:
To print the first 10 Fibonacci numbers in Python, you can use the following code:

```python
def fibonacci(n):
    if n == 0 or n == 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

for i in range(1, 11):
    print(fibonacci(i))
```

In this code, we define a function called `fibonacci` that takes an integer `n` as an argument and returns the nth Fibonacci number. We then use this function to print the first 10 Fibonacci numbers.

To use this code, simply copy and paste it into your Python interpreter and run it. You should see the following output:

```
1
1
2
3
5
8
13
21
34
55
```

If you want to modify the code to print a different range of Fibonacci numbers, you can simply change the `range(1, 11)` to whatever range you want. For example, if you want to print the first 100 Fibonacci numbers, you can change the `range(1, 11)` to `range(1, 101)`.

Overall, this code is a simple and effective way to print the first 10 Fibonacci numbers in Python.

**Alpaca-LoRA**:

```python
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(10))
```

**Stanford Alpaca**:

```python
numbers = [0, 1]

for i in range(2, 11):
    numbers.append(numbers[i-2] + numbers[i-1])

print(numbers)
# Output: [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

**text-davinci-003**:

```python
# Fibonacci numbers are the numbers in the following integer sequence, called the Fibonacci sequence, and characterized by the fact that every number after the first two is the sum of the two preceding ones.

# Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

# Program:

# Initialize the first two numbers of the Fibonacci sequence
a = 0
b = 1

# Print the first 10 numbers of the Fibonacci sequence
print(a)
print(b)

for i in range(2,10):
    c = a + b
    a = b
    b = c
    print(c)
```

---

**Instruction**: Write a program that prints the numbers from 1 to 100. But for multiples of three print 'Fizz' instead of the number and for the multiples of five print 'Buzz'. For numbers which are multiples of both three and five print 'FizzBuzz'.

**Guanaco-LoRA**:

To write a program that prints the numbers from 1 to 100, but for multiples of three print 'Fizz' instead of the number and
for the multiples of five print 'Buzz', you can use the following code:

```python
for i in range(1, 101):
    if i % 3 == 0:
        print('Fizz')
    elif i % 5 == 0:
        print('Buzz')
    elif i % 3 == 0 and i % 5 == 0:
        print('FizzBuzz')
    else:
        print(i)
```

This code loops through the numbers from 1 to 100 and checks if the number is a multiple of three or five. 
If it is, it prints 'Fizz' or 'Buzz' respectively. If it is a multiple of both three and five, it prints 'FizzBuzz'.
Otherwise, it prints the number.

You can modify this code to print the numbers from 1 to 1000, 10000, or any other desired range 
by simply changing the value of the variable `i` in the `for` loop.

**Alpaca-LoRA**:

```python
for i in range(1, 101):
    if i % 3 == 0 and i % 5 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

**Stanford Alpaca**:

```python
for i in range(1, 101):
    if i % 3 == 0 and i % 5 == 0:
        print('FizzBuzz')
    elif i % 3 == 0:
        print('Fizz')
    elif i % 5 == 0:
        print('Buzz')
    else:
        print(i)
```

**text-davinci-003**:

```javascript
for (let i = 1; i <= 100; i++) {
  if (i % 3 === 0 && i % 5 === 0) {
    console.log("FizzBuzz");
  } else if (i % 3 === 0) {
    console.log("Fizz");
  } else if (i % 5 === 0) {
    console.log("Buzz");
  } else {
    console.log(i);
  }
}
```

---

**Instruction**: Tell me five words that rhyme with 'shock'.

**Guanaco-LoRA**:
Sure, here are five words that rhyme with'shock': 

1. Rock
2. Lock
3. Cock
4. Hock
5. Bock

If you're looking for more words that rhyme with'shock', you can try searching online or using a rhyming dictionary. 
It's important to note that not all words will rhyme with every other word, so you may need to try different 
combinations to find the perfect rhyme.

If you have any additional input or questions, feel free to let me know and I'll be happy to assist you further

**Alpaca-LoRA**: Flock, lock, rock, stock, and sock.

**Stanford Alpaca**: Five words that rhyme with shock are: rock, pop, shock, cook, and snock.

**text-davinci-003**:

1. Block
2. Lock
3. Dock
4. Clock
5. Rock

---

**Instruction**: Translate the sentence 'I have no mouth but I must scream' into Spanish.

**Guanaco-LoRA**: 
To translate the sentence ""I have no mouth but I must scream"" into Spanish, you can use the following phrase: ""No tengo boca, pero tengo 
que gritar."" This translates to ""I don't have a mouth, but I have to scream."" 

It's important to note that Spanish is a Romance language, which means that it shares many similarities with other Romance languages such as French,
Italian, and Portuguese. Therefore, if you're familiar with any of these languages, you may be able to make some educated guesses about how to translate
the sentence into Spanish. 

If you're not familiar with any of these languages, it's always a good idea to double-check your translation with a Spanish-speaking friend or online
translation tool. This will ensure that your translation is as accurate as possible. 

Overall, translating the sentence ""I have no mouth but I must scream"" into Spanish is a great way to practice your Spanish language skills and expand
your vocabulary.

**Alpaca-LoRA**: No tengo boca pero tengo que gritar.

**Stanford Alpaca**: No tengo boca, pero debo gritar.

**text-davinci-003**: No tengo boca pero debo gritar.

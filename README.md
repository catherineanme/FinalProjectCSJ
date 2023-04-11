**Our CS32 Final Project Repository!**


Welcome to our CS32 Final Project! As Artificial Intelligence (AI) becomes more prevalent in today's world, we realized that so many people are scared of, or worried about, the powers of AI because it is difficult to understand as so much happens behind the scenes in code. In order to make the process of AI more understandable and accessible, we aim to create a simple game and have AI play that game, evolving with each round played. After each round, we will print out how the computer 'learned' from the previous, and prompt the human viewer to think about how the computer might 'evolve' for the next round. This final project is a teaching tool for people who want to learn more about the basics of AI, and to help AI become more approachable.


**The learning objectives for our supposed student are as follows:**
Understand that an AI program will ‘evolve’ to solve a specific problem with repetition
Understand that there are different parameters that impact this evolution, so when we change these parameters, it can change how the AI evolves. 
Have a visual familiarity with simple AI, so that it doesn’t seem as scary when interacting with in the future! 

**Our current learning objectives for us as students are as follows:**
Learn how to implement AI into this game 
Learn about how to make an effective lesson plan and think about which elements of our program to highlight in order to make the ideas conveyed digestible to the student. We’ve found so far that learning how to teach this forces us to understand the forms and functions of artificial intelligence more comprehensively! 


**Our ‘wishlist’ for our project, and what we plan to do in the next few weeks:**

A game that the computer plays, stopping at the end of each round to display a worksheet or reflection question that helps walk the student through what is happening on-screen. In our ideal world, the final product would essentially be a learning module. In order to streamline this process, we are going to first CODE THE GAME, and then record that game being played and insert it into a simple Google-Slides online learning module that contains explanatory text.


**Inputs for our game’s script:**
Meta-Parameters
Population Size 
Number of Generations 
Mutation Factor 


**What we want our game’s script to output:** 
We want the game to be similar to the game Geometry Dash with an artificially intelligent twist: it’ll get better at the game with each round it plays. We want to be able to watch these rounds so we can screen-record them and put the videos into the learning module. 


Here's a sample of the mutation program that we have been building. This code takes an array and creates a list of inputs and outputs. 

def BreedMutate(array): #input is an array of tuples, sorted by tup[1]
    sortedList = array
    length = int(len(sortedList)*0.5) #this is of the yValues
    fittest = sortedList[length:]
    children = []
    for parent in fittest:
        ix = fittest.index(parent)
        if(ix%2 == 1):
            offspring = (fittest[ix][0] + fittest[ix-1][0]) * 0.5
            children.append([offspring, yValIndiv(offspring)])
            #print(offspring)
    #print(children)
    noise = np.random.normal(0,0.25,len(array))
    for i in range(len(children)):
        mutated = children[i][0] + noise[i]
        if(mutated > 4):
            mutated = 4
        elif(mutated < 0):
            mutated = 0
        sortedList.append([mutated, yValIndiv(mutated)])
    #now we want to sort again by fit and kill the lowest three performers
    newSortedList = sorted(sortedList, key=lambda tup: tup[1]) #this is where we sort at the end, so that the input for the next iteration is sorted\
    x = []
    y = []
    for i in range(len(newSortedList)):
        x.append(newSortedList[i][0])
        y.append(newSortedList[i][1])
    return newSortedList[3:] #this kills 3 weakest
    
    
    We found Geometry Dash on GitHub already coded in Python by Yonah Aviv from MIT. We are using this code as a base and then are going to incorporate our AI model into it. We had to realize that coding this AI is really difficult, and learning the pygames library to make a complete game with graphics, etc. is a heavy task to combine with making our own mutating AI system & educational model! 
    
    So from now on, we are buidling these mutations and learning how to make this program work / build to it, and learning how to incorporate AI into the game. We already begun writing up mini-modules that correspond with different things that we ourselves have learned throughout this process, AND very introductory texts for people who have zero knowledge at all! IF we have time towards the end of our project, we could try to make our own game but we really want to focus on the AI / education components. 






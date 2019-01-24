So recently my martial arts instructor Sifu Kurt Cornwell at MKG Detroit asked me for some context about what programming is due to some discussions around how I think about programming. This is my attempt at answering the questions: what is programming? why do you do it? can you teach me a tiny bit about it so I can get a basic feel for it?

In this writing, I'll be comparing it to martial arts training I've been part of in MKG Detroit, since it's a common language and will be good for analogies about how I think about programming. It may not be the best analogies for everyone.

## Ok. First, programming is telling computers what to do. 
Computers are very dumb, but very very very fast. So if you tell it to do something, but didn't say it the right way, the computer will do the wrong thing very very very fast, or fail at doing anything and throw up a giant wall of text (the error message) telling you in excrutiating detail what went wrong. The error message can be very annoying and frustrating - I'd compare it to seeing someone do double stick for the first time, and correcting them on the most detailed thing they're doing wrong. It's not a great way to get feedback, but if you figure out how to read the feedback, error messages actually very informative (most of the time).

Ex of simple error messages:
```
>>> print x
  File "<stdin>", line 1
    print x
          ^
SyntaxError: Missing parentheses in call to 'print'. Did you mean print(x)?
>>> print(x)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'x' is not defined
>>> print("x")
x
```
in this example, I'm in the terminal (a basic place to run a program), and I started up the python programming language. The first error message is: `SyntaxError: Missing parentheses in call to 'print'. Did you mean print(x)?` basically is telling me that I missed parenthesis which are required by python when printing. The second error message is: `NameError: name 'x' is not defined` is saying that the variable x is not defined. I then make it work by putting quotes around the x making it a string constant instead of a variable.

ok... I didn't explain a few things there

- variable: something that stores data. for example, if you told me to feed an angle 3, but didn't preset it by specifying the numbering system we're using, I don't technically know what you want since you've taught me 2-3 different numbering systems.

- syntax: the language/format that python expects you to speak in. Basically it expects you to only use Kali and not use Muay Thai, so `print x` is invalid, as is `print(x)` where x isn't defined, but `print("x")` is exactly what python can handle. These minor variations can be very annoying for beginners, but once you've learned the language fairly well, they fade into the background and get easier to avoid/spot in the same way that if you walked into a gym you could probably spot the grappler from the muay thai fighter, but a typical person off the street wouldn't know the difference. 

- Integrated Development Environment (IDE): is a specialized text editor used by programmers that does some fancy stuff that catch and highlight syntax errors (and provide many other benefits) like in my error example above, the IDE would have highlighted the invalid options. You could think of this as a coach that guides you in correcting bad form in martial arts.

One of the reasons I like programming is that it's so very technical. There's a bit of a thrill or rush or sense of accomplishment when you can get the stupid computer to do something specific that's actually what you wanted. Similar to teaching someone kali and seeing them start correcting some of the errors they started out with. 

Another cool thing is you can build cool shit with software that's very useful to people. Like recently I read [this article](https://jalopnik.com/how-i-collected-the-data-for-our-latest-story-on-credit-1829667459) about collecting data about court cases and determining how a certain company was using the courts as a collections agency. The data analysis would have been incredibly difficult without computers, but with some website scraping (programatically reading data from the website and picking out the important details you want, then aggregating them into a report), they were able to do a good analysis with minimal man-hours. 

## Ok... taking a look at the questions I'm attempting to answer...

### What is programming? 
Another definition of programing I operate by is: getting the right data to the right people (or other programs) at the right time. You see this in websites like Facebook attempting to give you your favorite friends posts as they write them. or purchasing websites showing you products, then giving a system your purchase orders (and money), then giving the seller a list of what you want, then giving the seller shipping labels, the notifying you when it's shipped/arrived. This is all just moving data around to the correct spots using computers. Programs talk to eachother all the time via something called an API. 

- Application Programming Interface (API): basically a way for one program to give another data, request data, or request an action. so a purchasing website on purchase, calls an api (maybe paypall or stripe) specific to transfering money so that the actual website doesn't need to deal with, store, or otherwise manage specialty topics like money transfers. 
  
so an api interaction would be like a ring coach telling the fighter what sequence to try, the coach specializes in determining what will get past the oponents guard, the fighter specializes in actually implementing the fight. so the purchasing website specializes in determining what people might want to buy while paypall or stripe or some other company/system specializes in collecting the money. This is how a lot of the web works. you find or build or get someone else to build an api to do some specialty action or handle some special data, then the api can be used by one or a thousand different website, similar to how one coach could corner for 1 or 5 or 100 fighters (I actually don't know how that side of fighting works beyond some random stories I've heard through other martial artists)

## terminology
- functions: a piece of code separated to it's own section that does a specific thing. this can be used in multiple spots. so say I wanted to call the `do_drills` function from above outside of class, I could do that as well.

Building blocks of programming that you see in different programming languages even when they have different syntax (similar to how pretty much every martial art has a jab):

1. data / data structures (which hold data)
   1. constants as part of the language. examples are raw strings usually surrounded by quotes, numbers  (integers, double, float),
   2. array/list/enumeratable (a list of data/constants/other data structures, I envision this as a weekly pill container with Monday-Sunday on it, it could hold pills, water, paper, air, farts, paper clips, ect...)
   3. dictionary/map - similar to a library catalogue, you search for a specific book and it tells you where in the library it is, these have a key, and a value. key is usually a string, value can be anything - say raw data like a string or another data structure. 
   4. variable - holds/names a specific piece of data or data structure so it's easy to use later
2. basic control structures
   1. if/else (basic branching, if you feed an angle 1, I do inside deflection, if you feed angle 2, I do outside deflection)
   2. loops: while you're feeding, I evade. 
3. organization concepts
   1. function - does a specific thing, think of it as a verb
   2. class - think of this as a noun. it has data and functions - basically Theo would be the class, if you call my `set_numbering_system(1-5)`, that would pre-set me with a numbering system. then if you call my feed function with some data specifying the angle: ex: `feed(1)`, I'll react with the correct feed. if you then call my feed function again `feed(2)` I look up my internal data, see we're using the `1-5` angle system, and feed the correct angle 2.
   3. program - made up of a bunch of classes and functions, will provide some (maybe multiple) ways to call it to do specific things. Facebook would be multiple programs interacting with eachother. one program might be your feed, one might be adds, one might be chat, one might be games, one might be the one that pulls all the others together to format all the parts into one specific page. each complex in their own right. each may talk with others via api's. 
4. Comments
   1. usually separated out by special syntax, this doesn't get run and is just notes for the programmer. if you see `#` in this file, everything after it is a comment.




## back to the questions: can you teach me a tiny bit of it?
Ok, so there's a concept called pseudo code. Basically it's using the concepts of coding to write a program in shorthand that a programming language won't actually be able to run.

Ex:
Psuedo code:
```
if during_class
    do_drills
```

actual syntactically correct code:
```
def during_class():
    return True

def do_drills():
    print("look, everyone is doing the drill perfectly!!")

if during_class():
    do_drills()
```
which would print out the text `look, everyone is doing the drill perfectly!!`

as you can see, the pseudo code gets a decent idea of the code across without worrying about the syntax of the specific language or the details of functions.

so:
variable:
`minutes_per_round = 4`
4 is the data, x is the variable name. whenever I need to know the number of minutes in a round, I just access this variable instead of typing 4. that way if we want 3 minute rounds, 2 minute rounds, or 20 minute rounds, I just change it in one place. 

If I have another piece of data, say `drills_per_round = 4`, the data is still 4, but the variable name is different. now I can change the number of drills in a round separately from the minutes in a round. by using variables, it makes programs easier to modify and easier to read. 

Let's write some pseudo code for the muay thai rounds class on Fridays.

```
demo_partner = "Joe" # variable demo_partner is set to the data "Joe"
round_time = 3 # variable round_time is set to the data 3 - potential better name would be: round_time_in_minutes
break_time = 1
number_of_rounds = 3

def set_timer(round, break): # function definition, takes 2 pieces of data, first piece is the round time, second piece is the break time, within the definition of this function, the are stored in the variables `round` and `break`, not whatever variable names were passed in
    pass # ignoring definition for now

write_drills_on_board() # a function
demo_drills(demo_partner) # a function where we pass the variable `demo_partner` which currently contains the string data "Joe"

set_timer(round_time, break_time)
start_timer()

for(int i = 0; i < number_of_rounds; i++):  # this is a control structure, a basic loop that starts at 0, and goes for however long is stored in the variable number_of_rounds, in this case 3
    do_drills()

switch_feeder()
demo_partner = "Dana"

demo_drills(demo_partner)
start_timer()

for(int i = 0; i < number_of_rounds; i++):
    do_drills()

collapse()
```

Making a program readable is the MOST important part of programming. 

Making a program readable is the MOST important part of programming. It has the same level of importance as keeping your heel up in martial arts.

This is because if you can't read the program and understand it, you can't safely modify it. If you can't make your code readable to other people working on it, they won't reuse your code and will instead duplicate the code you wrote in a way that they can read/understand.

A lot of programming is making pieces of code reuseable. Another chunck of programming is abstracting away implementation details so the code calling you just calls the function `start_timer()` instead of dealing with the hardware in computers that deals specifically with keeping time. The biggest and most frustrating part of programming is determining what needs to be built.

In the pseudo code for Friday's rounds class, I have abstracted away all the implementation details and mostly just left the data and some readable functions. the timer section of the code would interface with the programming timers. might be very straightforward, might be a pain in the ass to implement depending on the language.

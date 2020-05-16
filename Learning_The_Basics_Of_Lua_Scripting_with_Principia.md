# Learning Lua Coding with Principia
Note: This lesson is written for Principia users but beginner lua users may find it more friendly and useful than the other online guides (just buy Principia already it's cheap and awesome). All information is as of Principia 1.5.0.4 and is subject to author ignorance!

## Lesson #1: Getting started

### Part I: Don't Panic!
Looking at a complex code can be quite intimidating for those who have never even considered programming anything"¦ but I assure you it's not nearly as bad as you think. Many of the Principia users are very young and many do not use english as their first language so I will keep thse lessons free of most programming terms and write as if the reader has never seen a code before. Also these lessons will focus on some of the basic commands and format of the code and will not be covering most Principia specific things like 'controlling the adventure robot' with luascript.

### Part II: What you need to know before you begin.
While most of the online examples use text in the majority of thier examples, coding = 90% math stuff, plain and simple. Good news is 90% of the math stuff is pretty basic. It will help you greatly if you have an understanding of basic algebra, geometry and a healthy respect for the equation `a^2+b^2=c^2`. Anything you will want to do with curves and circles, which is more than you might think, will require Pythagrius' help. Knowledge of the X/Y grid system and negative values will be needed and this lesson will also assume that you have a basic understanding of the 0.0-1.0 signaling system used in Principia or something similar.

### Part III: Gotta start somewhere!
Pick a very simple idea and try to discover a coding solution"¦ Most of the commands you will learn one at a time looking at other examples, help levels and tutorials or by reading the wiki. Through repetition and patience you can create great works with only a few techniques. As you improve your skills with these few techniques you will find yourself able to figure out each of your coding puzzles more easily and might even find yourself able to create things from scratch simply by thinking about it for awhile"¦ The singular most important thing you need to master is the 'if then' command, but first you will need to know about how to format your codebox so it will run on Principia.

If you open a luascript box you will find some strange words and symbols called functions, a function is simply a part of a code that is pre-made and runs in a section by itself, like a tool to a carpenter. The first section is,

```lua
function init(is_sandbox)
end
```

You will not need the 'is_sandbox' for this lesson but it wont hurt anything, you will notice there are no capital letters in the 'function init' command, all codes are case sensitive.

```lua
function init()
end
```

**init()** is the section where we put all of our codes that only need to run once at the beginning of the program. There might be nothing at all, in which case you can erase it entirely"¦ or it might be very, very long depending on what you are making. Everything from your pixel map(graphic images) to variables get set here. Not running commands constantly is very important to good code management. There will be much more on that later.

### Part IV: Variables and numbers

Variables are placeholders for numbers or words. This is so things can be shorter and easier to remember. When I refer to numbers I am talking about anything which might represent a number.

Example Numbers: `0`, `-50.12`, `1/7`, `1+1`, `(23/52*(0.012-2))`, `math.pi`, `math.min(math.pi,370)`, `math.sqrt((A*A)+(B*B))`, `100%25` (see part VI)

math.pi is the permanent placeholder for the number 'pi', math.min is equal to the lowest of the values seperated by commas inside the brackets(Arguments) and math.sqrt is the square root of the value inside the brackets in this case the value of 'C' in the equation A^2 + B^2 = C^2. 'A' and 'B' are examples of variables. If you were to use the 'sqrt' example it would cause an error because the value of 'A' and 'B' are undefined, So we begin our first actual code by defining some values for 'A' and 'B',

```lua
function init()
	A=5
	B=10
end
```

If we put these lines outside the init() in the step() portion of the code, it will tell the computer "a=5 B=10, a=5 B=10, a=5 B=10"¦ 125 times per second, since it only needs to be told once it goes into the init() section"¦ Our first goal is to determine the value of 'C' based on the two variables. Since we do not plan on changing the values of 'A' and 'B' we also put our pythagrian equation inside the init() function,

```lua
function init()
	A=5
	B=10
	C=math.sqrt((A*A)+(B*B))
end
```

Now when the program is run, the value of 'C' will be calculated once before the rest of the code begins and we will be able to use 'C' as a number in place of the three code lines it took to figure it out.

Many things will produce one or more variables which you will have to name first, for example the function game:get_cursor() lets you find the x and y position of the mouse or touch cursor. you will need to name them first:

```lua
CursorX,CursorY=game:get_cursor()
```

### Part V: Formatting 101 and coding style

You may have already noticed that each person will write their codes a little bit differently, even though the codes may be doing the exact same thing. The computer reads the lines as one long wall of text, any extra spacing at the beginning of a line or line changes are simply to help us read it. The following codes are all identical as far as the computer is concerned.

```lua
function init()
	A=5
	B=10
	C=math.sqrt((A*A)+(B*B))
end
```

```lua
function init()
	A,B=5,10;
	C = math.sqrt(( A * A ) + ( B * B )) end

function init() A=5 B=10 C=math.sqrt((A*A)+(B*B)) end

--This code was written by Jimmy "The greatest coder ever" Wilson
function init(); A , B = 5 , 10 ; C=math.sqrt((A*A)+(B*B)); end;
--wasn't it awesome!!!!!
```

The ';' symbol is ignored by the program and is very popular among coders, it is simply used as a visual clue to indicate the end each individual section of code. A line change is considered as a space and will break for the next chunk, anything written after a '--' will be ignored on that one line. All of the codes are identical, but the bottom three would be considered more "sloppy" and difficult to read. Do whatever you are most comfortable with, just don't be surprised if you ask for help and nobody can read your sloppy codes ;) The many styles can make figuring out a code difficult and intimidating, but once you learn the basics you will be able to ignore many things.

### Part VI: Running a program, --if/then #1, find remainder, debugging with game:show_numfeed(), game:set_score(), and

If you only put codes inside the **init()** function, it will do exactly nothing, principia runs at 125 hertz or "bits" per second. That means your step() code is being read through 125 times per second. If your creation produces a lot of lag it may mean that you have written something wrong or extremely memory intensive and the code cannot figure out what to do or can't keep up. All of the codes we will be using go inside the second function found in the default luascript box,

```lua
function step(count)
end
```

There are some special functions which run outside of the step() function but they are rarely needed and are for more advanced coding techniques.

```lua
function step(count)
	game:show_numfeed(count,0)
	game:set_score(count)
end
```

Our Devs were kind enough to impliment a variable into the step() function called 'count'. You can use count a great deal as it is a very helpful number, count is equal to the number of bits the program has been running. If you leave your program running for a long time this number can get very big indeed but it is still helpful. **game:show_numfeed(number)** is used to show a number at the top of the screen when running a program, while useful as a display number it should be used during play testing to find errors in your calculations and make sure your numbers are behaving as intended, a.k.a debugging. The number after the comma is how many decimal places you wish to show, the example above will show the total bit count. **game:set_score(value)** will display the value minus the decimal in the score position, if you have display score enabled.

Our first programs will use the count variable to make a few simple timers, turn on the score display to test it. You can rename the count variable to whatever you wish, I prefer "bit" but will use the default name for the lessons. Every line you write in the step() function will run constantly unless you tell it not to,

```lua
function init()
	Ten_Second_Timer = 0
end
```

First we set a variable for one our timers, some people like to use long variable names that explain exactly what they represent. The underscore '_' is used as any other letter and is a common way to create an artifical space in the variable name. This timer is set to begin counting from zero.

*The lua "find remainder" quick command is an extremely useful tool for managing numbers, learn it well. It is used by putting '%value' behind any number, the result is the number divided by the "value""¦ so 25%10 will divide 25 /10 = 2 +5r... it discards the 2 and return the remainder number.. 5*

```lua
function step(count)
	EveryBitTimer = count/125

	if count % 1250 == 0 then
		Ten_Second_Timer = Ten_Second_Timer+10
	end

	game:show_numfeed(EveryBitTimer,3)
	game:set_score(Ten_Second_Timer)
end
```

The every bit timer is very easy to figure out, just divide the current bit count by 125"¦ every time through the code the value of the variable will increase by .008 or 1/125. The ten second variable refers to itself and therefor needs to be initialized above, it uses our first if/then command"¦ an if/then command can be read like this,

```
IF (this condition is met) THEN (do this) END
IF (the remainder of: current bit count/1250 equals zero) THEN
	(add ten to the current value of the variable named Ten_Second_Timer) END
```

You will note that the if "condition" uses a double '='"¦ any = in the condition spot must be double for some inexplicable reason.

Lastly we can skip a few steps get rid of the extra variable and put one of the timers dierctly into the set score position"¦ as your coding gets better you will be able to shrink your codes into shorter versions, the minimum needed for a simple timer is this,

```lua
function step(t)
	game:set_score(t/125)
end
```

### Part VII: No substitute for testing
I can only speak from my own experience so I would highly recommend learning by constant playtesting and repetition. Reading about it is nice but without actually putting the codes into the box and pressing play, you wont learn much. Find a simple code made by someone else and playtest it thouroughly until you have a better grasp on that particular code. Maybe you'll even improve it!

Find a code, change a number and press play to see what happens, keep changing things until you can try to write it from scratch. A good place to start is with my Lua School Basics level, it has codes which behave the same as many of the parts in Principia. If you know how the part works it will help you understand the associated code. Many of the old examples use "if this:first_run() then" in place of the new "function init()" you will have to change this to use the older codes. Also new is the step function"¦ to use old codes you will have to place everything that is listed outside of the "first run" into a "function step() (insert old code here) end" command.

Everything I know about programming comes from making levels and testing things on Principia over the last 9 months, my knowledge is still quite limited but I feel confident that I could make most super-nintendo quality games at this point"¦ While it may take you longer than me it IS possible for you to learn a great deal in a short time and be on your way to making wonders! Hell I cant even look at my microwave without thinking "I could make that!"

## Lesson #2: Loving the if
The if/then command can be used to accomplish almost anything you want to do"¦ most of the other commands are used to make the codes shorter so you don't have to do so much work, but a good knowledge of if/then alone can open up infinite possibilties to you.

### Part I: if/then/else, memory basics, game:add_score, or

```lua
function init()
	MyNumber=500
end

function step(count)
	if count <= MyNumber then
		game:set_score(1)
	else
		game:set_score(2)
	end
end
```

```
IF (this condition is met) THEN (do this) ELSE (if the condition is not met, do this instead) END
IF (the current bit count is less than or equal to 500) THEN
	(display 1 on the score counter) ELSE (if the current bit count is greater than or equal to 500, display 2 on the score counter) END
```

This code will make the score equal one for the first four seconds and then swicth it to two permanently after that. While it will work perfectly, it is poorly written and uses more memory than it should, I will try to give you some good habits before you learn the bad ones. Currently it is checking to see if the condition is met on every bit the program runs, but this is unnessesary. Here is a better code and since we are not using the variable 500 more than once I will eliminate the init() part of the code"¦

```lua
function step(count)
	if count == 1 or count == 500 then
		game:add_score(1)
	end
end
```

Now it is as small as can be, this simple code will only be read on bit#1 and bit#500. The game already tracks a score on every bit, so you can skip that part. Like the count variable you can treat the score as a second in game variable already provided and initialized at 0. You can use this variable even if the score isnt being displayed by using **game:get_score**... If the **game:add_score(1)** was outside the if/then command it would add 1 to the score 125 times per second. It can also be used to add negative numbers to the score. The 'or' in the code above is another of the basic tools you will use"¦ It is important to remember that all of the conditions must be spelled out,

```lua
if count == 1 or 500 then
```

The above code will not work and will create an error.

### Part II: Nesting, this:read(0), elseif, and

Nesting is when you put one code inside of another, the code on the inside will only be run if the parent code is happy. this:read(0) is how you read the 0-1 signal number from the IN0 socket of the luascript object, if nothing is plugged in then it will be 0.0

```lua
function step()
	if this:read(0) == 1 then
		if this:read(1) == 1 then
			game:add_score(2)
		else
			game:add_score(1)
		end
	end
end
```

The code above will add +1 to the score every bit where the signal from IN0 equals 1 and the signal from IN1 does not equal ~=1. It will add +2 if both inputs equal =1. The following codes are identical to the one above,

(SETUP:Make two RC buttons and send the wires to the luascript IN0 and IN1, try it with and without Sparsifiers.)
```lua
function step()
	if this:read(0) == 1 and this:read(1) < 1 then
		game:add_score(1)
	end
	if this:read(0) == 1 and this:read(1) == 1 then
		game:add_score(2)
	end
end

function step()
	TotalSignal = this:read(0) + this:read(1)
	if this:read(0) > 0 and TotalSignal == 1 then
		game:add_score(1)
	elseif TotalSignal == 2 then
		game:add_score(2)
	end
end
```

Since the TotalSignal variable is reading the inputs it needs to be set outside of the **init()** so it can read every bit. 'elseif' can be used to add more specific conditions without needing a huge string of 'end's to close it, the stuff inside the 'elseif' wont run if the parent condition is satisfied. 'and' is another of the basic tools in your arsenal, it's pretty much what is sounds like and it works much like the Principia object.

### Part III: is between?, this:write(0), ~= (not equal to)

(SETUP: Wire a grapher to luaout0, RC(slider OUT0)--luaIN0)
```lua
function step()
	in0 = this:read(0)
	if in0 ~= 0 then
		if in0 <= 0.25 then
			this:write(0, 0.25)
			game:set_score(25)
		elseif in0 > 0.25 and in0 <= 0.5 then
			this:write(0, 0.5)
			game:set_score(50)
		elseif in0 > 0.5 and in0 <= 0.75 then
			this:write(0, 0.75)
			game:set_score(75)
		elseif in0 > 0.75 then
			this:write(0, 1)
			game:set_score(100)
		end
	end
end
```

Here we begin by shortening the name of the in0 input.. The ~= sign is used for "not equal to", another useful tool for your belt. If the in0 signal is anything but 0.0 then it checks the in0 signal and does the list of actions. There is no shortcut for "Is between" but you may need it often, use the >= or < method above"¦ If the in0 signal is 0.25 or less then send a .25 signal to out0 on the luascript and set the score at 25. If it isn't 0.25 or less(elseif) see if it is more than 0.25 and less than or equal to 0.5, if it is then send 0.5 to out0 and set the score to 50"¦ and so on.

### Part IV: nil , Formatting 102

If you call for a variable or table or other item that is not defined you will get an error which tells you the thing you are looking for is 'nil', this means it does not exist"¦yet. You can use nil in a multitude of ways to improve your codes. Normally you might define your variable in the **init()**, but this isnt always needed,

(SETUP: RC with a sparsified button sent to in0"¦ RC--sparsifier--luaIN0)
```lua
function step()
	in0 = this:read(0)

	if in0 == 1 then
		if A == nil then
			A=0
		end

		if A < 10 then
			A = A + 1
		else
			A = nil
		end
	end

	if A ~= nil then
		game:show_numfeed(A)
	end
end
```

The order in which you write things can be critical to the operation of you code. Since we did not initialize 'A' in the **init()**, 'A' = nil to begin with. if we were to write the code in this order,

```lua
if A < 10 then
	A = A + 1
else
	A = nil
end

if A == nil then
	A = 0
end
```

...an error will occur since it cannot compare A to the number 10 until 'A' is not nil. If the 'A==nil then A=0' part comes first, it can then recognize the 0<10. We now have a code which will add up from 1 to 10 by one each time the RC button is pressed. On the eleventh press 'A' is returned to nil. And finally if 'A' does not equal nil the value of 'A' will be shown in the numfeed spot.

Returning things to nil when they are no longer needed can be a good way to manage memory, for example you might have a character creation program where you have a large selection of data to choose from, after the character type is selected, all of the data for the other traits is no longer needed and could be turned back to nil.

## Lesson #3: for/do loops

The for/do loop is your second primary weapon along with the if/then command. A for/do loop is used to repeat a code many times. Each time it repeats a special variable increases each time making the result of the code different each time. It will repeat until the number of loops you set is reached and then move on to the next line of code. These examples will use the default loop setting which increases the loop variable by 1 each time through.

### Part I: For/do basics, this:write_frequency()

```lua
function step()
	this:write_frequency(1, .1)
	this:write_frequency(2, .2)
	this:write_frequency(3, .3)
	this:write_frequency(4, .4)
	this:write_frequency(5, .5)

	for MyLoop = 6, 10 do
		this:write_frequency(MyLoop, MyLoop / 10)
	end
end
```

This code sends a signal to all 10 frequencies from 1-10, each signal is one tenth of the number of the frequency. The first 5 are set one at a time with copy and paste. Six through Ten are set with the for/do loop. The write_frequency line runs five times in a row with the value of 'MyLoop' increasing by one each time(6,7,8,9,10). It begins with the first number and ends with the second number. The order the numbers loop might be critical to the code you are working on, later we'll learn how to reverse the order.

### Part II: Multi-purpose loops, this:read_frequency(), this:listen_on_frequency()

Principia has some special requirements to make things work smoothly, to use read_frequency(). you must first "listen_on" the frequency you want to read. you may need to use a lot of frequencies, in which case you'll want to use a for/do loop.

```lua
function init()
	for i = 1, 100 do
		this:listen_on_frequency(i)
	end
end
```

We are now ready to read all frequencies from 1-100,

```lua
function step()
	for i = 1, 100 do
		if this:read_frequency(i) == 1 then
			this:write_frequency(i + 100, 1)
		end
	end
end
```

As you can see this method is vastly preferrable to writing out the three lines of code 100 times each. This simple code just sends any frequency from 1-100 that is reading 1.0 to the corresponding frequency +100 higher(1,101...99,199).

Below we begin to make a more sophisticated loop, starting by only listening to every other frequency from 1-99, we do this by multiplying every number from 1-50 by two and subtracting one.

```lua
function init()
	for LoopV = 1, 50 do
		this:listen_on_frequency((LoopV * 2) - 1)
	end
end

function step()
	for LoopV = 1, 50 do
		if this:read_frequency((LoopV * 2) - 1) == 1 then
			this:write_frequency(LoopV * 2, 1)
		end
	end
end
```

We are now detecting every odd frequency from 1-100 and if it is 1.0 we send it on to the even numbered frequency above it(1->2, 99->100)

### Part III: Alternate loop spacing and reverse ordering

By adding a third number to the loop variable you can change the amount the loop increases each time from +1.0. The loops below work the same as the ones above by simply increasing by 2 each loop instead one, you do not need to use whole numbers any type of number will do.

```lua
function init()
	for LoopV=1,99,2 do
		this:listen_on_frequency(LoopV)
	end
end

function step()
	for LoopV=1,99,2 do
		if this:read_frequency(LoopV)==1 then
			this:write_frequency(LoopV+1, 1)
		end
	end
end
```

You may want to reverse the order of the loop, to do so you only need list the larger number first and use a negative number in the 3rd "count by" position.

```lua
for LoopV = 99, 1, -2 do
	if this:read_frequency(LoopV) == 1 then
		this:write_frequency(LoopV + 1, 1)
	end
end
```

Or as always you can "invert" a value by subtracting your results from the higher value of your scale...

```lua
for LoopV = 1, 99, 2 do
	if this:read_frequency(LoopV) == 1 then
		this:write_frequency(101 - LoopV, 1)
	end
end
```

This version sends 1.0 to frequency #100 if frequency #1 =1.0... if frequency #3 = 1.0 then it sends to frequency #98 and so on.

### Part IV: Double for/do loops, grid basics, this:draw_sprite

Double for/do loops are a critical method to learn and the first thing you will encounter which may actually lag your program if used incorrectly or abused. We will be using these for many of the future examples. When you nest one loop inside another it will perform the # of loops from the first code * the # of loops in the second code and can get out of hand very quickly. Before learning the details about how to manipulate sprites and graphics we are going to use a default sprite to help us test.

```lua
this:draw_sprite(0, 0, 0, 0.5, 0.5, 0, 0, 1, 1)
```

The first two numbers are the X location and Y location that the sprite will be drawn in the world, for now we will only be using those two numbers. The code above will draw a square sprite 0.5 wide and 0.5 tall at world location 0x,0y. The order things are drawn is very important to sprites, sprites listed later in the code will draw on top of the ones earlier in the code.

Our goal is to draw 100 sprites at every coordinate location from 1x,1y to 10x,10y, we do this with a double for/do loop,

```lua
function step()
	for X = 1, 10 do
		for Y = 1, 10 do
			this:draw_sprite(x, y, 0, 0.5, 0.5, 0, 0, 1, 1)
		end
	end
end
```

This for/do loops a total of 100 times before moving on to the next line of the code. it begins at X=1, Y=1 and then moves up completing the inner loop for all ten Y positions at X=1. After that X becomes 2 and the inner Y loop repeats again. If you need the grid to scale in a different direction you may need to re-organise the double loop. You can set the Y direction to be the outer loop or invert some of the numbers to do this.

You can quickly overwhelm your program by making large nested for/do loops, a double loop from 1-100 will perform 10,000 actions before moving on to the next part of code, multiplied by *125 times per second means the 100x double for/do loop is performing 1.25 million actions per second. You may need to find alternate methods for codes with such large requirements.

## Lesson #4: Tables

Also refered to as arrays, lists or databases... Tables are used to store lots of different peices of data in one easy to access location. Tables can store any kind of data including other tables... the number of things you can do with tables is too large for me to cover so we will focus on a few of the basics. Loops are an essential part of mananging most tables so we will be using them together,

### Part I: True/False

In many cases you will need to initialize an empty table before you begin,

```lua
function init()
	tableA={}
end
```

Won't need to initialize the empty table if we bigin by initializing it with some data inside, table data is listed in brackets like so,

```lua
function init()
	tableA = { this:read(0) * 10, 10, 100, 1000, math.pi * 2 }
end
```

Each of the positions in the table can be identified by several methods, first is with a position number[1],

```lua
function step()
	if tableA[1] < tableA[2] then
		MyVar = true else
		MyVar = false
	end
	if MyVar = true then
		game:show_numfeed(tableA[3])
	end
end
```

Now we've created a variable on the fly called MyVar, it uses true/false instead of numbers. Like the numbers it needs to be initialized unless you give it special instructions. With the code above MyVar will always be either true or false if the first two table positions are numbers, so it does not need to be initialized. The MyVar will always equal true unless the signal to in0 equals 1.0. then we use the true/false state to activate the number feed showing tableA[3]... 100.

If your code changes one of the initial values of either tableA[1] or tableA[2] to something that isnt a number, an error will occur. An error will also occur if you ask for the true/false state of MyVar, before it is defined. Here are some codes which will produce errors,

```lua
function step()
	if MyVar == false and tableA[1] < tableA[2] then
		MyVar = true
	end
end

function step()
	if tableA[1] < tableA[2] then
		MyVar = true
	else
		MyVar = false
	end

	tableA[1] = "my random non-number text string"
	tableA[1] = true
end
```

### Part II: Random is life

As a maker of games I use random numbers like they are going out of style, even if you dont want to make games, knowing how to customize random numbers is a must. There are two methods, math.random() and math.random(lowvalue, highvalue). The first method is generic and creates a number from 0.0-1.0 by .01, the second method is custom and will only make values in increments of one.

```lua
-- a random value from 0.00-1.00 by increments of .01
math.random()
-- random between either 0.0 or 1.0
math.random(0, 1)
-- a whole number from -100 to 25
math.random(-100, 25)
-- a number from 1.25-10.25 by increments of 1, any value over 9.25 returns the next highest number. Will always start at the first number and increase by 1.
math.random(1.25, 10)
-- Two dice simulator, 36 combinations from 2-12 weighted towards 7
math.random(1, 6) + math.random(1, 6)
```

As you can see this is somewhat restrictive, to make your randoms more versitile you need to modify the result.

```lua
-- a random value from 0.0 to 10.0 by .1
math.random() * 10
-- random between either 0.0, 0.5 or 1.0
math.random(0, 2) / 2
-- a random value from 0.000 to 1.000 by increments of .001
math.random(1, 1000) / 1000
-- a random even number from 0 to 100
math.random(0, 50) * 2
-- a random odd number from 1 to 99
(math.random(1, 50) * 2) - 1
-- a random number from 1 to 298 by increments of 3, (1,4,7,10...etc.)
(math.random(1, 100) * 3) - 2
```

To move things randomly right/left or up/down you will need a number that is random in the negative or positive direction, here are a few methods.

```lua
-- a random value from -1.00 to 1.00 by increments of .01
math.random(-100,100)/100
-- a random value either -1.0 or 1.0
(math.random(0,1)*2)-1
```

The last example above is a great multi-purpose tool you can multiply it by a second random number or this:read(0) to create a positive to negative scale.

Finally we make a random number between four completely unrelated values with a simple table,

(SETUP: RC with a sparsified button sent to in0"¦ RC--sparsifier--luaIN0)
```lua
function init()
	randoValues = {0.12, 100, 999 * 999, math.min(1, math.max(3, math.pi))}
	A = randoValues[math.random(1, #randoValues)]
end
function step()
	if this:read(0) == 1 then
		A = randoValues[math.random(1, #randoValues)]
	end
	game:show_numfeed(A)
end
```

Every time the button is pressed a random number between 1 and the #length of the table is created, we can use the table length [#randoValues] instead of 1-4 so if we decide to add more entries to the table the random will automattically adjust(see part IV). It then finds the number at the table position of the random number.

### Part III: Managing data 101, Using for/do with tables

In this next example we want a table listing the first 100 numbers and the square roots of each number to follow after each one,

```lua
T = {1, math.sqrt(1), 2, math.sqrt(2), 3,...}
```

...but we don't want to have to write out each entry one at a time, so we'll need to coordinate a for/do loop to do it for us.

```lua
function init()
	T={}
	for value=1,100 do
		T[{value*2}-1]=value
		T[value*2]=math.sqrt(value)
		this:listen_on_frequency(value)
	end
end
```

Now every other entry starting with T[1] is a whole number counting up from 1 to 100. and every even numbered table entry is the square root of that number. While we're at it we listen on 100 frequencies from 1-100.

Let's now make use of the data in the program.

```lua
function step()
	for v = 1, 100 do
		if this:read_frequency(v) >= 0.5 then
			this:write_frequency(v * 2, T[value * 2]/100)
		end
	end
end
```

Now we have 100 luascript if-gates that will send a square root value/100 to frequencies 101-200 if the corresponding 1-100 frequency is greater than or equal to 0.5.

### Part IV: Table length, merging tables, count timers

The length of a table is often the most useful number for sorting things out, every code requirement is a little bit different and you will need to be able to rearrainge your data sometimes to fit with the other codes you have already written.

```lua
function init()
	tableA = {1,2,3,4,5}
	tableB = {6,7,8,9,10,11,12}
end
```

To find the length of a table use a # sign in front of the table name. It's common to need the length of the table so you can count off each position to compare the values or change them in some way. Putting the table length as the end point for a for/do loop is one use and another is if you need to add on to the end of a table with new entries you can use the 'current table length"+1 (#table+1)

This example will add all of the entries from the second table at the end of the first and then get rid of the second table entries when the count reaches 8 seconds(1000 bits),

```lua
function step(count)
	if count = 1000 then
		for v = 1, #tableB do
			tableA[#tableA+v] = tableB[v]
			tableB = {}
		end
	end
end
```

The length of tableB is 7 so we tell it to make 7 new table entries to the end of tableA. The length of tableA is 5 so we need it to number the new entries at #tableA+v or 5+(1-7) and each is assigned the value of tableB[entries 1-7] or (6-12). Last we clear all entries from tableB, we could make tableB 'nil' but we plan on using it again.

Now I'm going to change up the previous code so that it can accept new entries to tableB, wait 8 more seconds and then again add them to the end of tableA.

(SETUP: RC(button)--sparsifier--luaIN0)
```lua
function init()
	tableA={10,20,30,40,50}
	tableB={60,70,80,90,100,110,120}
	bitNumber=0
end

function step(count)
	if count = bitNumber + 1000 then
		for v = 1, #tableB do
			tableA[#tableA+v] = tableB[v]
			tableB = {}
		end
	end

	if this:read(0) == 1 and tableB[1] = nil then
		tableB[1] = (#tableA + 1) * 10
		bitNumber = count
	end
end
```

Now you have a button that does nothing until 8 seconds has passed, after that time TableB adds itself to the end of tableA. Then the button is unlocked since tableB[1] is now nil, pressing the button creates a new tableB[1] with the correct value based on the formula needed. Finally when you press the button the 'bitNumber' variable becomes the current bit count#, restarting the 8 second clock automatically for another 1000 bits.

### Part V: Tables in Tables in Tables, draw_sprite()

Now we are going to make a table called MySprites where each position is filled with another table containing four numbers.

```lua
function init()
	Sprites = {}
	Sprites[1] = {0,0,2,0.3}
	Sprites[2] = {4,0,1,1}
	Sprites[3] = {2,5,10,0.5}
end
```

This can also be written as,

```lua
function init()
	Sprites = {}
	Sprites { {0,0,2,0.3}, {4,0,1,1}, {2,5,10,0.5} }
end
```

The first two numbers in each sub-table are the X and Y locations I want to draw my sprites at. The 3rd and 4th numbers are the X-size (width) and Y-size (height) of the sprites. To retreive one of the values of the sub tables you add another [] bracket to the end of the table name. MySprite[3][3] will pull the third number in the MySprite[3] table ... the 10.

Now to draw some generic sprites at the location and size we want by combining all we've learned so far!

```lua
function step()
	for sNum = 1, #Sprites do
		this:draw_sprite(Sprites[sNum][1], Sprites{sNum][2], 0, Sprites[sNum][3], Sprites[sNum][4],0,0,1,1)
	end
end
```

### Part VI: Making a pattern sprite, set_sprite_texel, sprite_filtering **\*NEW\***

Each lua box has a sprite sheet which defaults to 128x128 pixels(texels) You can set the individual texels in the **init()** or do many all at the same time with equations or patterns... The following method is the easiest for managing a picture since it can easily be modified if a texel is out of place or needs a color change. We start by defining some colors we want to use in a new type of table set-up.

```lua
function init()
	a = {R = 0, G = 0, B = 0, A = 0} --black(100% transparent)
	b = {R = 1, G = 0, B = 0, A = 2} --red solid color
	MyPattern={
		a,a,a,a,a,a,a,a,a,a,a,a,a,
		a,a,b,b,b,a,a,b,b,b,b,a,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,b,b,b,b,a,b,b,b,b,a,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,b,b,b,a,a,
		a,a,a,a,a,a,a,a,a,a,a,a,a}
	ResolutionX=13
	ResolutionY=9
```

So we've made a table with 117 positions in it. It's been formatted into a grid array so a visual pattern can be seen by the user and customized. The pattern is intended to show two letters A and B in red. The computer is going to read the table as one long line, it does not care one bit that we've made a fancy pattern... What we need is a grid management equation that will tell the computer to sort the table like our eyeballs do.

This is pretty complex and you do not need to understand the following code completely to make good use of it.

```lua
	for y = 0, ResolutionY - 1 do
		for x = 0, ResolutionX - 1 do
			color=MyPattern[1 + y * ResolutionX + x]
			this:set_sprite_texel(x, ResolutionY - y - 1, color.R, color.G,color.B, color.A)
		end
	end
end --{end of init()}
```

**this:set_sprite_texel()** is used to set each individually colored texel by it's x/y coordinate location. The first two numbers are the x and y location of the texel you want to set. The sprite sheet begins at location 0x,0y in the lower left corner upto 127x/127y in the top right. This double for/do loop begins at y=0 and then cycles through the inner loop for all x values. After completing this first row, y becomes 1 and the x loop begins again for the row 2 texels. Since we begin the loop at 0 the loop must end at our desired resolution minus 1.

b={R=1,G=0,B=0,A=2}, this is the second method for calling for data from a table... the first table position is no longer a plain number but the variable 'R', to retrieve this data point you can use the shortcut b.R.

Above the for/do loop creates a special type of temporary table, since the 'color' line will produce one result for every table position it can be used as a table for the remainder of the loop. So instead of calling for b.R we call for color.R.

y begins at 0 and x begins at 0, if you input those values into the equation:[1+y*ResolutionX+x] you get [1+0*13+0] = [1+[0*13]+0] = 1, so the very first position in our new color table = 1.

```lua
y=0 x=0		= [1+[0*13]+0]	= 1
y=0 x=12	= [1+[0*13]+12]	= 13
y=1 x=0		= [1+[1*13]+0]	= 14	--start row 2
y=9 x=12	= [1+[8*13]+12]	= 117	--last position
```

so.. color=MyPattern[1] through MyPattern(117]

Now when the set texel calls for color it is cycling through all 117 table positions and finding the .R, .G, .B, .A for each position. The data still needs to be sorted to the correct texel position.

```lua
this:set_sprite_texel(x,ResolutionY-y-1...
```

So x will match the current loop x value as it cycles through, y is more special it begins at 13 since 13 is the top row in our pattern and the first position in the table is the top right texel of the pattern, 12y 0x.

You will notice Ive left a single layer of transparent texels surrounding each image. this is so I can use the **sprite_filtering()** function.

```lua
this:set_sprite_filtering(0) --this will draw all texels as solid squares, very 8-bit. No transparent edges are needed if you are using this.
this:set_sprite_filtering(1) --this setting blends all texel colors with the texels surrounding it.
```

If you tried to show a transparent texel with a solid texel next to it in the pattern, it will appear as a transparent smear of the adjacent colors.

By leaving a gap between the edges and each pattern image you can draw a pattern without any edge blending problems. Usually seen as a thin line on one or more of the edges.

When making a pattern sprite I usually create a big temporary sprite which will display the whole sheet so you can see how things are looking,

```lua
function step()
	this:draw_sprite(0,0,0,10,10,0,0,127,127)
end
```

Currently our pattern is drawn in the lower left of the sheet, if we want to move it from that spot you simply add to the x/y set_texel locations like so,

```lua
function init()
	this:set_sprite_texel(x + 40, ResolutionY - y - 1 + 20, color.R, color.G, color.B, color.A)
end
```

Now its drawing from 40x and 20y instead of 0x and 0y. to display only the two letters and not the rest of the blank sprite sheet we have to isolate a section of the sheet with the last four numbers in the **draw_sprite()**.

```lua
function step()
	this:draw_sprite(0,0,0,2,2,1,1,12,8)
end
```

Now we are drawing a rectangle section of the grid from texel x1/21 to x1/y7. It should have no lines around the edges and display AB at the 0x,0y location designated.

Now we also need to adjust the size of the sprite to account for the fact that our letters are 5x by 7y, any attempt to draw a square sprite will squish the height of the picture...

```lua
this:draw_sprite(0,0,0,2,2*(7/5),1,1,12,8)
```

Lastly Ill show the entire code but with the two letter images split into separate sprites drawn at 0x/0y and 3x/0y,

```lua
function init()
	this:set_sprite_filtering(1)
	a = {R = 0, G = 0, B = 0, A = 0} --black(100% transparent)
	b = {R = 1, G = 0, B = 0, A = 2} --red solid color

	MyPattern={
		a,a,a,a,a,a,a,a,a,a,a,a,a,
		a,a,b,b,b,a,a,b,b,b,b,a,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,b,b,b,b,a,b,b,b,b,a,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,a,a,a,b,a,
		a,b,a,a,a,b,a,b,b,b,b,a,a,
		a,a,a,a,a,a,a,a,a,a,a,a,a}

	ResolutionX=13
	ResolutionY=9

	for y=0,ResolutionY-1 do
		for x=0,ResolutionX-1 do
			color=MyPattern[1+y*ResolutionX+x]
			this:set_sprite_texel(x,ResolutionY-y-1,color.R,color.G,color.B,color.A)
		end
	end
	this:set_sprite_texel(x,ResolutionY-y-1,color.R,color.G,color.B,color.A)
end

function step()
	this:draw_sprite(0,0,0,2,2*(7/5),1,1,6,8) --draw the letter A
	this:draw_sprite(3,0,0,2,2*(7/5),7,1,11,8) --draw the letter B
end
```

Conclusion,

With the information in these four lessons you can create almost anything, you will even be able to look at other programming languages and not be completely lost. I do plan on adding more info for the while/do loop and repeat/until, however they are so rarely actually needed you can get by without them for now.

I would reccomend moving on to my 20 part Lua Sprite Mega Tutorial level or Lua School Basics on Principia. They cover almost everything you need to know about drawing sprites, angles, creating graphics and the codes for the existing parts. I also have a Lua Line Draw Mega Tutorial and a Lua 101 series of levels with lots of stuff on it... #7 has most of the math shortcuts like math.min(), but I made that when I didnt know so much. I also reccomend "SinCos and you!" for understanding circles better...I also have 100+ other lua based levels you can look over.

I may add more lessons with stuff on circles/curves, grid mastery, text strings and other tricks of the trade if Im feeling up to it. I wanted to keep this lesson mostly number based since it is the universal language and Principia doesnt use a lot of text... if you understand how to use these techniques with numbers using them to manipulate words will be easier.

Good Luck, be patient, determine where to start and take it one step at a time, playtest other levels, ask questions, keep at it, learn 100's of ways not to do things, change a number, press play, see what happens... you shall prevail!

Thanks to Team Bithack for an awesome product and everyone who helped me learn!

--zardOz
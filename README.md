# Lab 1.5 Chat (Part 1)

## Instructions

You are going to write a program that you can have a conversation with. This program will evolve over several labs. In this version you will be able to say (or rather, type) something to your program and it will respond appropriately.

All Java programs start by executing the main method. This is where you will always write the code that "bootstraps" your program.

This particular program will greet the user with a friendly message, then allow the user to type something into the program. It will then *process* that input to generate a response and output the response to the user.

For example:

The program will output:

```
Hello.
```

Then it will wait for the user to type something and press enter.

```
Right back at you
```

Then it will output a response.

```
That's interesting.
```

And the program will end. All together the output will look something like this:

```
Hello.
Right back at you
That's interesting.
```

The starter code will manage all of the input/output of the program. The process method will do all the magic to generate an appropriate response.

### Part 1: Startup Code

In the main method you will do the following:

1. Output the message "Hello."
2. Instantiate a Scanner object
3. Use the nextLine Scanner method to read an entire line of text from the user
4. Call the process method and pass it the input from the user
5. Output the response that was returned from the process method.

Use the System.out.println method to output strings to the user:

```
System.out.println("Display This");
```

The following statement will instantiate an instance of a Scanner object and store it in a variable named *input*.

```
Scanner input = new Scanner(System.in);
```

You used several Scanner methods in a previous lab. Those methods would read a single *word* as input. For this program we want to read everything the user types until they press the enter key. You can use the readLine method to accomlpish this.

```
input.readLine()
```

Don't forget to assign the return value to a variable!

You should pass the user's input as an argument to the process method and store the value returned into a variable. Then you should output that value.

Since you haven't written the process method yet, it will return the value *null* instead of an appropriate response. For now, that is okay.

Test your program. It should say "Hello.", then you should type something in and press enter. Then it should output "null" and the program should end.

### Part 2: Process Method

For starters, make this method always return the message "That's interesting.". Test your program to make sure when you type a message in, it outputs "That's interesting" like this:

```
Hello.
Computer Science!
That's interesting.
```

Now that you know the process method is being called and the value it returns is being output to the screen, you can make it respond to certain kinds of inputs.

You will make this program respond differently if the input message contains any of the words "dog", "weather" or "tacos".

1. If the message contains the string "dog" then the process method should return the value "Dogs are fun."
2. If the message contains the string "weather" then the process method should return the value "Is it raining?"
3. If the message contains the string "tacos" then the process method should return the value "Tacos are great!"
4. And, if the message doesn't include any of those words, then the process method should return the value "That's interesting."

First, make your program respond appropriately to messages that contain the string "dog". Test your code to make sure it works correctly. Test it with both inputs that contain "dog" and inputs that do not contain "dog"

Examples:

* "I have to walk my dog before school" -> "Dogs are fun."
* "Do you have a pet dog" -> "Dogs are fun."
* "dog parks are a good place to make friends" -> "Dogs are fun."
* "Do you like cats?" -> "That's interesting."

Remember to make your program respond appropriately to messages that contain the string "dog", "weather", and "tacos".

Pro Tip:

There is are string methods that will convert all the characters of a string to lowercase or uppercase. You can use these methods to easily match the string "dog" with "Dog", "DOG", and "DoG".

```
String input = "Some TeXt wiTh wEIrd CapiTAlizaTIoN"

String lower = input.toLowerCase(); //some text with weird capitalization
String upper = input.toUpperCase(); //SOME TEXT WITH WEIRD CAPITALIZATION
```

### Part 3: "I Want X" Statements

You will make your program respond to messages that are in the form "I want X" by saying "Why do you want X?"

Examples:

* "I want tacos" -> "Why do you want tacos?"
* "I want to get an A" -> "Why do you want to get an A?"
* "I don't want to stop" -> "That's interesting."

You have to write code in two methods to accomplish this task. First, the process method needs to inspect the input message and determine if it is an "I want" statement. If it is, then it should pass the message as an argument to the processIWantStatement method and use the processIWantStatement method's return value as the response.

Hint: What String method can you use to identify if a small string is contained at a particular location in a bigger string?

Then, you need to write the processIWantStatement method so that it returns the correct response. You need to write code in this method that extracts what the user wants from the message, and constructs a new String in the format "Why do you want X?".

Don't forget the question mark at the end of the response!

Hint: If you knew the index of the X in "I want X" was, what String method could you use to extract that portion of the message? How can you figure out the index of X in "I want X"?

Note: Make sure you don't change the capitalization of the user's input. For example, if the user inputs "I want TaCoS" then your program should response "Why do you want TaCoS?"

### Part 4: "I X You" Statements

You will make your program respond to messages that are in the form "I X you" by saying "Why do you X me?".

Examples:

* "I see you" -> "Why do you see me?"
* "I want to sing to you" -> "Why do you want to sing to me?"

You will implement this similarly to how you implemented the processIWantStatement method. The process method needs to identify whether the message meets the pattern "I X you", pass the message to the processIYouStatement method, then the processIYouStatement method should extract the X from "I x you" and construct the response "Why do you X me?"

Note: Your program should continue to respond appropriately to "I want X" messages if they don't end with the string "you".

## Testing

Run your program and enter different messages. Make sure you get the appropriate response from your program. Make sure to test your code for situations where your if-statement should evaluate to true, and for situations where your if-statement should evaluate to false.

For example, consider the following pseudocode:

```
if( input contains "dog" )
{
  output: "Dogs are my favorite!"
}
else
{
  output: "I'd rather talk about dogs."
}
```

You should test this code by inputting a message that contains the word "dog" and you should also test it with a message that does not contain the word "dog".

## Grading

This lab will be automatically graded by comparing the output of the program to the expected output. If your output matches the expected output, then you will receive credit for this lab.

## Turning it in

When you have finished this lab, upload it to [MrMayCS.com/turnitin](http://mrmaycs.com/turnitin)

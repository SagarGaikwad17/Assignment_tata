# Assignment_tata


A. Descriptive Questions:

1. Can we nest the Scaffold widget? Why or Why not?

-Yes, you can nest a Scaffold , It is just a widget, so you can put it anywhere .


2. What are the different ways we can create a custom widget ?

-composition , using plugin and package we can creat a custom widget .

3. How can I access platform(iOS or Android) specific code from Flutter?

-Flutter uses a flexible system to call platform-specific API either available on Android in Java or Kotlin code, or in Objective-C or Swift code on iOS. The general idea of accessing the platform-specific code in Flutter is through the messaging protocol. The messages are passed between the client (UI) and Host (Platform) using the common message channel. It means the clients sends a message to the Host by using this message channel. Next, the Host listens on that message channel, receives the message, does the appropriate functionality, and finally returns the result to the client.


4. What is BuildContext? What is its importance?

-BuildContext is actually the widget's element in the Element tree  ,so every widget has its own BuildContext. You usually use BuildContext to get a reference to the theme or to another widget. For example, if you want to show a material dialog, you need a reference to the scaffold. You can get it with Scaffold.of(context), where context is the build context. of() searches up the tree until it finds the nearest scaffold.


B. Coding Questions:

1. Refactor the code below so that the children will wrap to the next line when the display width is small for them to fit.

-class LongStringwidget extends Statelesswidget {
@override
Widget butld(ButldContext context) {
return Wrap(children: [
Chip(Label: Text('I' )),
Chip(Label: Text( 'an' )),
Chip(label: Text( 'Looking* )),
Chip(label: Text('for' )), Chip(label: Text('a* )),
Chip(label: Text(' job' )),
Chip(label: Text( 'and' ))
Chip( label: Text('I' )),
Chip(Label: Text( 'need' 11
Chip( Label: Text('a* )),
Chip(label: Text(' job' )),
]);
  }
}


2. Identify the problem in the following code block and correct it.

-It blocks your app because counting to ten billion is a computationally expensive task, even for a computer.
Dart code runs inside its own area of memory called an isolate also known as memory thread. Each isolate has its own memory heap, which ensures that no isolate can access any other isolate's state.
Making it an async function wouldn't help, either, because it would still run on the same isolate.

Solution :- 

Future<String> makeSomeoneElseCountForMe() async {
  return await compute(LongOperationMethod, 10000000000);
}

String LongOperationMethod(int countTo) {
  var counting = 0;
  for (var i = 1; i <= countTo; i++) {
    counting = i;
  }
  return '$counting! Ready or not, here I come!';
}


3. In the below code, list1 declared with var, list2 with final and list3 with const. What is the difference between these lists? Will the last two lines compile?

-When using the var keyword, the Data type is inferred and its value can change. The following line is equivalent to the first line above, except that you explicitly declare the data type.

With final and const, you can’t reassign a new value after the initial assignment. final values are assigned once at runtime and a const variable value has to be either known at compile time, set, or hard coded before you run your app

The third line will compile. You’re not reassigning the list2 list itself, but changing the value of an item in the third index position (remember, indexes start with 0). Lists are mutable by default in Dart.
If you tried to do the following, though, it wouldn’t compile because you’re trying to reassign a final variable

The fourth line will not compile because the value of list1 isn’t assigned until runtime. 




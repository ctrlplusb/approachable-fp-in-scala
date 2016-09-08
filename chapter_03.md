# Chapter 3: Gearing up

It would be immensely useful if you had Scala set up on your machine. So in this chapter we will be doing just that. After we have our install humming along nicely I will then take you through a couple of ways that you can run some Scala code. This will be critical for you to participate in the upcoming exercises.

## Firstly, we will need Java

As Scala is a [JVM](https://en.wikipedia.org/wiki/Java_virtual_machine) powered language you will need to have Java installed. I recommend that you install the latest version of Java \(version 8 at the time of writing\) which will support the upcoming Scala 2.12 release.

To check if Java is installed on your machine open a console and type the following command:

```bash
java -version  
```

> The version number that you get back will likely be something like \`1.8.0\_25-b17\`. You can interpret this number by dropping the leading \`1.\` from it \(i.e. \`1.8.0\_25-b17\` becomes \`8.0\_25-b17\`\) in order to extract the commonly know major version number. The example being version 8.

If you received a "command not found" error message then you likely need to install Java. [You can find platform specific installation instructions for Java here](https://www.java.com/en/download/help/download_options.xml). After installing Java, ensure that it is installed correctly by running the above command again \(you may need to restart your console\).

## Scala is up next

Great, we have Java installed now, so lets go ahead and get Scala set up.  Go to the [download page](http://www.scala-lang.org/download/) and select the option to download the binaries \(at time of writing this was "Option 1"\). You should now have compressed file saved.  This compressed file contains everything you need to compile and run Scala code with.  It doesn't require any installation process, you simply need to uncompress it and you are good to go.  So choose an appropriate place in your system to host the files and move the compressed file there.  In my case I just created a \`scala\` folder in my user folder. After you have moved the file feel free to decompress it. You should then see a structure similar to the following:

```
/Users/Sean/scala/scala-2.11.8/
                              |- bin
                              |    |- scala
                              |    |- scalac
                              |    |- fsc
                              |- doc
                              |- lib
                              |- man
```

As you can see, the \`bin\` folder contains all the binary files we will need. We are going to be executing these binaries files often so it is in your best interests to add the full path to the \`bin\` directory to your system's respective PATH environment variable.  This will allow you to simply type \`scala\` in your console without prefixing it with the full path \(e.g. \`\/Users\/Sean\/scala\/scala-2.11-8\/bin\/scala\`\). If you have no idea how to add to your PATH environment variable, a quick Google search for your respective operating system will reveal some helpful instructions \(e.g. "add to the PATH on Mac OS X"\).

Once you have done the above test that all is well by opening a console and then type in the following:

```bash
scala -version
```

You should then see a message detailing the Scala version that you just installed.

## Executing Scala code

Now that you have Scala installed I will take you through a couple of the ways you can try out the language. I am only going to introduce a few "simple" techniques, just enough to get you go going through the next few chapters. Don't worry, we will cover some more "advanced" techniques, including Integrated Development Environments, in later chapters.

### The REPL

The Scala REPL allows you to execute Scala code within your console. It interprets your code immediately, returning the result. Some of its features are:

* Create and reuse variables \(including functions\)
* Multi-line support
* TAB completion\/suggestion
* Importing of libraries
* Pasting or importing of code

It's a great tool to quickly test the language with and develop your understanding.

**Starting the REPL**

To use it open a console and execute the following command:

```bash
scala
```

You should see something similar to the following \(if you didn't then you likely don't have Scala installed or configured on your PATH correctly\):

```bash
Welcome to Scala 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_101).
Type in expressions for evaluation. Or try :help
scala>
```

**Basic usage**

Try typing in the following and then press ENTER:

```bash
scala> val msg = "I am learning FP with Scala"
```

You should see a result similar to:

```bash
msg: String = I am learning FP with Scala
```

This is the REPL reporting that you have created a `val` with the name `msg` of type `String` and that its value is "I am learning FP with Scala".

You can reuse this `val` in subsequent commands. For example try executing the following:

```
val shoutedMsg = msg.toUpperCase
```

The above commands transforms the text contained within `msg`, converting it to uppercase, and then stores the result in a new `val` called `shoutedMsg`. You should have seen a result similar to the following:

```
shoutedMsg: String = I AM LEARNING FP WITH SCALA
```

> **TIP:** It can be tricky to remember all the variables you created as well as the methods that you can execute on them. The REPL recently added a super helpful auto-complete and suggestion feature. Try typing in \`shoute\` and then press the TAB key. The REPL should auto fill in the rest of name of your created variable \(i.e. \`shoutedMsg\`\). Now type a \`.\` character after the variable \(i.e. \`shoutedMsg.\`\) and press TAB again. You should see a list of all the methods available to the variable. You can partial type in one of the methods and then press TAB again to have the REPL auto-complete the rest.

**Exiting the REPL**

To quit the REPL execute the following command:

```
:quit
```

### Scripts

You can create simple Scala "script files" and execute them directly. For example, create a file called \`HelloWorld.scala\` and give it the following contents:

```
val msg = "Hello World!"
println(msg)
```

Don't worry about the syntax for now, we will cover it later. Save your file and then execute the following command in the same directory in which you created the \`HelloWorld.scala\` file:

```
scala HelloWorld.scala
```

You should have seen "Hello World" printed out in the console.

Script files also support the provision of command line arguments. You can access them by passing a 0-index based argument to the \`args\` method. For example rewrite your above script to look like the following:

```
val msg = "Hello " + args(0)
println(msg)
```

And then execute it like so:

```
scala HelloWorld.scala world
```

You should have seen "Hello World" printed out in the console.

Pretty cool hey? It's a nice easy way to get started and as your skills progress you may even decide to create some useful scripts for your day-to-day tasks. It's also nice for you to be able to save and revisit any of your experiments.


### Tips

#### What are Command Line Arguments?

Command Line Arguments are strings of text used in terminal (command line interface), and are typically used to set config or property values for an app. 


Syntax typically looks like:

`$ [runtime] [script_name] [argument-1 argument-2 argument-3 ... argument-n]`

Where:
* runtime = anything that executes a program or script (eg. node)
* arguments typically separated by spaces, but might be separated by commas

#### Benefits of Command Line Arguments?

1. Pass info to an app before it starts (eg. to config app settings)
2. Flexibility - CLA (strings) can be converted to other data types within the application
3. Useful for automated testing when CLAs are used with scripts and batch files
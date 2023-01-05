# Style guide for Arduino (work in progress)
*Created for students, hopefully useful for everybody.*


> Code is read more often than it is written. (Guido Van Rossum, creator of Python)

Arduino coding style guide, spurred from the lack of a comprehensive guide available on the internet and from the need to actually convince students to write their projects using more readable code and better practices.

Remember that a guide is just that, a guide. While some of the recommendation here are fundamental good practices, and it is highly recommended that you respect them, others are open to personal preferences. 

The current guide uses many sources for inspiration: from shamelessly copying (parts of) forum and blog posts with useful practices, to imitating the style of other coding guides. These have all been referenced in [References](#references) or in [Other style guides](#coding-guides). If I have missed anyone it is purely by mistake. Submit a PR and I will gladly adopt it.

Lastly, a style guide is a living document. It must constantly adapt to newer norms, technologies and techniques. The basis of any guide is its community. If you find this guide useful, please share it with other friends. If you notice a mistake or have updates to contribute, please submit a PR so that it can be adopted.
Check [Contributors](#contributors) to see a list of all the people that helped out.

## Table of contents
1. [Consistency](#consistency)
1. [Project structure](#project-structure)
1. [References](#references)
1. [Other style guides](#coding-guides)
1. [Contributors](#contributors)

## 1. Consistency
> Consistency is more important than which convention is used.

Guide or not, remember that consistency in code is of utmost importance. So, despite this guide (or other), use the same style in your code. If joining an already existing project, adapt to the coding style used there, and be consistent. Where possible, refactor early when you notice inconsistency in a project, but **be 100% sure** that you won't ruin any compatibilities.

**[⬆ back to top](#table-of-contents)**

## 2. Naming conventions
- Use descriptive, meaningful names for variables and functions. Avoid using short, generic names like "temp" or "count".
    > Why? Generic short names do not accurately reflect the purpose of the variable of function.
    ```arduino
    # Good:
    int temperature = 0;
    int counter = 0;
    ...
    void readTemperature() {
        // do stuff
    }
    ```

    ```arduino
    # Bad:
    int temp = 0;
    int count = 0;
    ...
    void readTemp() {
        // do stuff
    }
    ```

- 

**[⬆ back to top](#table-of-contents)**

## 2. Project-structure
Your code should explain itself, or use comments to do the same. Unless absolutely necessary, do not obfuscate your code for little gain in performance. 
- Start the project with a general comment that explain what the file (project) does
    > Why? So the reader gets a general understanding of the program early on
- Contiue with importing the necessary libraries
    > Why? Hopefully self-explanatory, but the imported libraries should one of the first lines of code
- Define constants and global variables
    > Why? So they are easy to find and see. Do not declare global variables in other random places in the program.
- Put your ```setup()``` and your ```loop()``` at the beginning of the program. 
    > Why? They help beginners to get an overview of the program, since all other functions are called from those two.

- Continue with your own functions, in a program-specific logic order.
    > Why? It makes the program easier to follow and debug.


    ```arduino
    # potentially good
    /*
        Sketch title

        Describe what it does in layman's terms.  Refer to the components
        attached to the various pins.

        The circuit:
        * list the components attached to each input
        * list the components attached to each output

        Created day month year
        By author's name
        Modified day month year
        By author's name

        http://github.com/<user>/<repo>/<file> (or other relevant link, if available)
    */

    const byte temperatureSensorPin = A0;

    int temperature = 0;

    void setup() {

    }

    void loop() {

    }

    // user defined
    void writeNumber(byte number) {
        // do stuff
    }
    ```


**[⬆ back to top](#table-of-contents)**


## 3. Comments
- Comment constants and variables whose usage are not obvious from the name
- Comment every code block. Do it before the block, such that the reader knows what's coming.
- Comment the foor loop
- Do not write comments that are obvious from the code block name

``` arduino
    # bad
    // write the number
    void writeNumber(byte number) {
        // do stuff
    }

    # potentially good
    /* 
    Displays the number on the 7 segment display. 
    Number can be between 0 and 9.
    */
    void writeNumber(byte number, byte decimalPoint) {
        // do stuff
    }
```


**[⬆ back to top](#table-of-contents)**

##

## References
References go here

**[⬆ back to top](#table-of-contents)**

## Other-coding-guides
Other coding guides, used for inspiration or just plain useful
- [C Coding Standard](https://users.ece.cmu.edu/~eno/coding/CCodingStandard.html)
- [Python PEP-8](https://peps.python.org/pep-0008/)
- [Python](https://github.com/kengz/python)
- [Ruby](https://github.com/rubocop/ruby-style-guide)
- [Airbnb JavaScript](https://github.com/airbnb/javascript)
- [AngularJS](https://github.com/mgechev/angularjs-style-guide)
- [Nick Gammon's Traps, tricks and style guide for Ardino](http://www.gammon.com.au/forum/?id=12153) (good advice, terrible spacing, though)
- [Arduino Writting Style Guide](https://docs.arduino.cc/learn/contributions/arduino-writing-style-guide)
- More will be added

**[⬆ back to top](#table-of-contents)**

# Contributors
Contributors list

**[⬆ back to top](#table-of-contents)**
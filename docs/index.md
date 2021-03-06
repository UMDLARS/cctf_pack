# Adversarial Program Debugging

> The following is a sample set of documentation from the PQL challenge,
> shown here for your reference. Feel free to use any of this that is helpful
> to you, or to remove it completely and write your own documentation from scratch.

Lord Dimwit Flathead has decreed that he wanted a simplified version of SQL that he named Prequel Query Language or PQL. Due to backwards compatibility requirements with an earlier database, [the PQL specification](https://docs.google.com/a/d.umn.edu/document/d/1dMTo4XEmmTN7pjUXIiwtl3KoIyTZI_F9q_jvdD9fMPU/edit?usp=sharing) also includes an on-disk database format. (It's less than ideal, but hey, that's backwards compatibility for you.) 

In order to get the best implementation possible, Lord Flathead has a strange approach: he divides his developers into teams and has them develop their own versions, attack the versions of the other teams, and repair their own versions in a capture the flag style exercise. You are a programmer for the FrobozzCo Magic Software Company on one of those teams. You have (hopefully) implemented your own version of the software in question. Your goal is to find errors or incorrect behavior in your own implementation and in the implementations of your peers by finding inputs that break them. Then, you'll fix the flaws in your own versions and your peers will try to fix theirs.

The winning team is the team with the least number of flaws in their version of PQL when time runs out.

# Table of Contents

 - [The Game](#the-game)
    - [Fixing Your Code and How to Submit](#fixing-your-code-and-how-to-submit)
    - [Collecting Flaws](#collecting-flaws)
 - [Program Behavior](#program-behavior)
 - [The Gold Standard](#the-gold-standard)

##### More resourcess
 - [Instructions on writing Instructions](./instructions)

### The Game

You are competing against the other teams to improve your version of your program while also attacking theirs. You will find flaws in the various implementations by developing "attack inputs" -- inputs that cause one or more implementations to behave incorrectly. Each attack file will have one attack string. Once you submit an attack, all implementations will be executed using the attack as input. The program will be tested to see if has the correct output and/or exit code and (optionally) whether any files the program creates are correct. Every attack that a team's implementation does not handle correctly will count against their score -- your goal is to be immune to as many attacks as possible.

#### Fixing Your Code and How to Submit

Your team will need to pull a copy of their source repo to the server. Your version should have all the files and executables as required in the [PQL specification](https://docs.google.com/a/d.umn.edu/document/d/1dMTo4XEmmTN7pjUXIiwtl3KoIyTZI_F9q_jvdD9fMPU/edit?usp=sharing), namely a program called `build` that makes a program called `pql` that behaves according to the spec.  

When you have a version of your program that you think is improved over the previous version, you should execute the command `submit` while in the source directory. `submit` will copy your program to a private directory for testing.

#### Collecting Flaws

Each known flaw that your team discovers should be collected in the directory `~/attacks/`. We recommend that you use your favorite editor to write attack files -- one attack per file. An attack file consists of a file of input to the program, such as a set of PQL queries as defined by [the specification](https://docs.google.com/a/d.umn.edu/document/d/1dMTo4XEmmTN7pjUXIiwtl3KoIyTZI_F9q_jvdD9fMPU/edit?usp=sharing). The scoring code will consume your attacks to test everyones' code.

### Program Behavior

The behavior of your program, including input, output, return code, and on disk data format (if applicable) is defined in [the software specification](https://docs.google.com/a/d.umn.edu/document/d/1dMTo4XEmmTN7pjUXIiwtl3KoIyTZI_F9q_jvdD9fMPU/edit?usp=sharing).

### The Gold Standard

In order to help verify your code, the Vizards of Vim Mountain (led by the powerful Brammoolenaar), provided your boss with a "perfect" version of the program, called 'gold'. You can use 'gold' to test the correct behavior for a particular input to make sure that your program is correct. Unfortunately, because the `gold` program was created using arcane magic, it exists in an alternative dimension, has no source code, and can't be used in production.  Still, you can run `gold` with arguments to test the "proper" behavior of the calculator.

Of course, it's likely that you might find flaws in gold that the Vizards overlooked. If that happens, simply cry out to the Vizards in a loud voice about the problem; they will hear your cry and attempt to fix it.


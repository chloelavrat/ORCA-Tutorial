 # ORCA / Part 2 / Basics

This part is dedicated to basic operators, structures and possibilities. At the end of this part, you will be able to produce basic sequences and rhythms with only 7 operators!

### Synthesis environment

As ORCA is a MIDI signal processor, its output contains only synthesizer control information.
So, to get an audio signal to listen to, we will use the VCV Rack synthesizer environment. Note that this could be replaced by any other system with a midi or UDP interface. (pure data / SuperCollider / Live ableton ...)

This part will only use the patch named `patch-melo-rhythms.vcv` attached to the tutorial. This patch contains :

- 1 **Melodic Lead** on MIDI Channel 1
- 1 **Kick** on MIDI channel 2
- 1 **Snare** on MIDI channel 3
- 1 **Bass** on MIDI channel 4

![patch-melo-rhythms](patch-melo-rhythms.png)

### Get the Midi On !

Let's see how Orca handles Midi messages. First of all, in order to connect our beloved sequencer to VCV Rack, we need to select the Midi output in ORCA. This can be done with the following commands:

- Select the **output MIDI device** : press `CTRL+.`
- Select the **input MIDI device** : press `CTRL+,`

Select the one corresponding to VCV :)

### Our First Operator : MIDI OUT (:)

The **Midi Out** operator handles the transfer from Orca to your preferred synthesizer as follows:

```ORCA
<0>:<1><2><3><4><5>
```

- `<0>` : is the **Bang input** this **trigger** the midi out
- `<1>` : is the **MIDI Channel** (channel 0 in ORCA is chanel 1 in MIDI)
- `<2>` : is the **Octave**
- `<3>` : is the **Note**
- `<4>` : is the **Velocity**
- `<5>` : is the **gate lenght** lenght of the note

You can try this operator by **selecting the Kick** channel like so:

```
E.E..E..E.....E..E..E.....E..E..E.....E..E..E.....E..E..E.....:12A9.
```

But wait what?! What are theses `E` ??

### Our Second Operator : East (E)

Orca is designed around a key concept, the **cardinal directions**. Thus, the **E** operator is just a *Bang* (a trigger) moving towards the East. As a kiss is just a kiss, an **E**ast is just an **E**ast. As time goes by for **N**orth, **S**outh, **W**est. 

So when the **E**ast moves to the input of the midi operator, it triggers the **VCV kick.** if you want a nice four on the floor you just have to copy/paste:

```
E..E..E..E..E..E..E..E..E..E..E..E...:12A9.
```

But I can hear you behind your computer... "It's not a sequencer, it's a keyboard with one note" and I agree. That's why we're now going to look at a third operator.

### Our Third Operator : Track (T)

The **T**rack operator can save a sequence and repeat it in a continuous loop following the Orca's internal clock. You can use it as follows:

```
<0><1>T<2>
     <3>
```

- `<0>` : is the **Key input**, the placement of the reading head
- `<1>` : is the **Length** of the track
- `<2>` : is the **Sequence** of the the track
- `<3>` : is the **Output note** of the track

Now, our four on the floor is more reliable:

 ```
.2C..........
..08T.*.*.*.*
.....:12A9...
 ```

Have you noticed the new operator? Let's see how he acts :)

### Our Fourth Operator : Clock (C)

The **C**lock counts at the same speed as your frame rate, it outputs a value based on the division of your frame rate (modulo) and the maximum value of the Clock.

```
<0>C<1>
  <2>
```

- `<0>` : is the **Clock Rate** - Division of the global BPM
- `<1>` : is the **Clock Length** - Maximum range of the clock
- `<2>` : is the **Clock Output** - Give a number

The code below divides the overall speed  (aka. frame speed) in four steps and start counting them:

```
1C4
.0.
```

And, if you want a four on the floor:

```
4C4
.1.
```

###  Our Sixth Operator : Delay (D)

As you can see, the clock only gives value and no bangs! This is why **D**elay exists. **D**elay is like a clock but it simply produces a bang, you can use it as follows:

```
<0>D<1>
  <2>
```

- `<0>` : is the **Divide Rate** - Division of the global BPM
- `<1>` : is the **Divide Length** - Maximum range of the divider
- `<2>` : is the **Divide Output** - Give a number

So when you combine C&D, you can get some very interesting sequences:

```
.1D24C4..
..*:31G9.
```

### Our Seventh Operators : Jumper (J)

Now here is a very useful operator. It is simple but it will save you on many occasions. This module is... A Jumper! A Jumper is simply to jump a value from top to bottom as follows:

```
<0>
 J
<1>
```

- `<0>` : is the **Input Value**
- `<1>` : is the **Output Value**

Normally, at this stage it is possible to compose a very simple ensemble of 4 instruments (). 
I let you try.

Here is what I propose, note the interest and use of jumpers :smile:

```
.......................................
.......................................
..1C8....................C7............
...68T*...*..............07TGFDBEDC....
...........................G...........
.....:13A..............D2..J...........
.......................*:32G...........
..1C8..................................
...68T..*....*............C7...........
..........................07TCBEFDGG...
.....:22F9..................C..........
........................D3..J..........
.........................:02C..........
.......................................
.......................................
```

### Chapter conclusion

Hi gang! Now you can really compose like a pro under the Orca environment. But don't stop there, Orca offers a lot of features to generate amazing random sequences. I'll tell you about them in the next chapter. :smile: 








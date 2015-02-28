# Taking Sonic Pi Further

Sonic Pi is so awesome that there are too many features to mention in
just one tutorial! If you feel like you have got to grips with the
[first page](worksheet.md), and you would like to try some other ways to
code music, then follow the steps below.

## Adding effects

Modern synthesisers have the ability to add effects to sounds. Sonic Pi
is no different, you are able to add studio effects such as bitcrusher,
reverb, echo and distortion. Of course you have to use code to add the
effects!

1. In a new worksheet find a sample that you like for example `sample :guit_e_fifths`

1. Wrap the sample in an effects block like this:
    
    ```ruby
    with_fx :reverb do
      sample :guit_e_fifths
    end
    ```
    
1. You can chain effects on top of other effects by nesting the code like this:

    ```ruby
    with_fx :reverb do
      with_fx :distortion do
        sample :guit_e_fifths
      end  
    end
    ```
    
You'll now hear the guitar sample played through the distortion effect and then through the reverb. If you've messed around with guitars, this is like plugging your guitar into a distotion pedal, then the distortion pedal into a reverb pedal and then finally into the amp:

     guitar --> distortion --> reverb --> amplifier
    
1. Play around with some effects and add them to your music. Remember
that a complete list of effects can be found in the help panel of
Sonic Pi under **FX**.

## Modifying Parameters

On occasion, you might like to make sounds play for a longer time or at
a different rate. This can be achieved easily by modifying the
parameters of the code you are using.

Take `play 60`, for example.

1. Click on **Help** to open the help documents, then select **Lang** on
the left hand side, and scroll down to **play**. You will see some
examples of its use. So far you have used `play` without any parameters;
let's use some now. 

1. In a new worksheet type:

    ```ruby
    play 60, attack: 1, release: 3
    ```
    
1. Press the **play** button to hear how that one note sounds. Attack and release control the amplitude of a note over time.

1. Now change the values for attack and release to see how those parameters affect the note.

There are lots of parameters that can also change the way samples or
synths sound. Try changing the values for `cutoff:`, `pan:`, `rate:` or
`amp:`. For a full list of parameters for each synth click on the
**Help** icon, followed by **Synths**, select asynth and scroll down
to see a full explanation for each type of parameter that can be used
with that synth. Same goes for samples!

## Using rrand

Sonic Pi includes a number of functions that can add more interesting
elements to your music. A really fun function is `rrand`, which will
return a random value between two specified numbers. For a cool effect,
use `rrand` to make the cutoff bounce around.

1. In a blank worksheet type:

```ruby
use_synth :prophet
loop do
  play 70, attack: 0, release: 0.1, cutoff: 80
  sleep 0.25
end
```
    
1. Instead of passing  a number like `80` to the cutoff value, try `rrand(40, 120)` like this:

```ruby
use_synth :prophet
loop do
  play 70, attack: 0, release: 0.2, cutoff: rrand(60, 130)
  sleep 0.2
end
```

1. Next try experimenting using `rrand` with other parameters. For example, add `pan: rrand(-1, 1)` to the play chord line and then press **play**.    
    
## Using choose

Another great way of introducing some interesting behaviour is to
`choose` an item from a list. For example if we had the list
`[52, 55, 57, 59, 62, 64]` we could pick a random element by adding
`.choose` to the end. This is like picking a random letter from a
scrabble bag. Let's add this in to our little loop: 

```ruby
use_synth :prophet
loop do
  play [52, 55, 57, 59, 62, 64].choose, attack: 0, release: 0.1, cutoff: rrand(60, 130)
  sleep 0.2
end
```
  
## What's next?
- Try working through the full built-in tutorial within the *Help* system.
- Can you make your own samples and import them into Sonic Pi?
- Why not take a look at the [Sonic Pi Competition resource](http://www.raspberrypi.org/learning/sonic-pi-competition-2014/) and plan your submission for next year?
- Can you create a full original composition and share it with friends?


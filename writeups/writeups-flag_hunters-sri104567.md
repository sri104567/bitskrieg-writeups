# Flag Hunters- reverse engineering


## Approach
After downloading the python file and running the instance, a song popped up and we had to enter a word. so i ctrl+C'ed it and used cat on the 
python file. Then i saw a line in the code where there was a secret verse which would print the flag from a txt file which was not open-able.

flag = open('flag.txt', 'r').read()

secret_intro = \
'''Pico warriors rising, puzzles laid bare,
Solving each challenge with precision and flair.
With unity and skill, flags we deliver,
The ether’s ours to conquer, '''\
+ flag + '\n'

song_flag_hunters = secret_intro + (whole song)

Since there was a string input from out side during the song, i figured whatever key would unlock the secret verse would have to be written 
there.

## Solution
The secret_intro is present at the beginning of the text block, but as we can see from the future lines in the code, the song starts printing from the 
Verse 1
"def reader(song, startLabel):"
startLabel refers to the Verse 1.

The code loops between the verses and the refrain for 100 lines. Its written in the code that it splits when it encounters ";".
"
 while not finished and line_count < MAX_LINES:
    line_count += 1
    for line in song_lines[lip].split(';'):
      if line == '' and song_lines[lip] != '':
        continue"
So, if we type ';' at the point where it asks to sing along, whatever we type next gets interpreted as code, rather than just text and it 
compares it with the options it has ("refrain", "end" ,"return","crowd"). So whatever we type there becomes the intructuion for it the second 
time around. So when we type ;RETURN 0, it jumps all they way back to the line 0 of the code, where the secret verse is stored.
Therefore, we are supposed to input ;RETURN [0-3] for the secret verse to print. It is till 3 because the verse is four lines long.
Pico warriors rising, puzzles laid bare,
Solving each challenge with precision and flair.
With unity and skill, flags we deliver,
The ether’s ours to conquer, academy{70637h3r_f0r3v3r_4943a085}
## Flag
 academy{70637h3r_f0r3v3r_4943a085}

## Takeaway
I learnt a little bit more of how to read python from this challenge.

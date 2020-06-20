# NoteConversors
This programs take part in the development of my final university project. I have made this program to check the viability of the Wavetable sintesis to generate sound. This method uses a linear interpolation formula between sound samples. This program applies Waveteble sintesis to the sound samples of a .wav file, consequently generates another .wav file with the result of use the before mentioned formula. There are two differents implementations of this formula, one made using floating point arithmetic (folder NoteConversor_double_3) and the other one, using fix point arithmetic (folder NoteConversor_fix_3).

Use make to generate the executable. Differents levels of optimization are defined in the makefile.

## How to use

In order to execute this program, It's needed to define as arguments the location of the input .wav file (preceding by -F), the location where the generated .wav file will be stored (preceding by -O, the output file is going to have almost the same name as the input file, the only different will reside at the ending of the name with the "_cool" sentence). In case the defined location after -O doesn't refers to a location in the system, the route of this location will be added at the end of the name of the output file. 

It also needed to define the target frequecy (preceding by -T) and the base frequency (preceding by  -B), both must be defined as notes following by the american note coding representation ( Do:C, Re:D, Mi:E, Fa:F, Sol:G, La:A, Si:B ). The aplication includes all the frequency of the 88 notes of a piano, starting in A0 and ending in C8 ( the number is a reference to the octave, must be included ). The base frequency refers to the frequency of the note stored in the input file, the program don't find out the corresponding frequency of a note, It must be defined as an argument ( preceding by  -B, as I have mentioned before ). If the base frequency is wrong, you won't obtain the expected result :)  

This project is also provided with two shell scripts, one of them generates all the 88 notes of a piano (generateNotes.sh) which are saved as .wav file in differents folders. All these generated files with the corresponding folder, could be easily removed using the other shell script (cleanNotes.sh). 
The folders Fur_Elise and Twinkle Twinkle_Twinkle_Little_Star contains the corresponding notes to play the firsts notes for each song.


## Commands examples
	
  >./wav_parser_op3.elf -F notasBuenas/C4v8.wav -O notasFlama/ -T C#4 -B C4

  >./wav_parser_op3.elf -F notasBuenas/A4v8.wav -O notasFlama/ -T B4 -B A4

  > ./wav_parser.elf -F ../48.8Khz24bit_Sorted/C4v8.wav -O iii -T C#4 -B C4

  > sh cleanNotes.sh

  > sh generateNotes.sh
## Additional Notes
The .wav files in the SameSize-1.06MB are originally from the [FreePats project](http://freepats.zenvoid.org/Piano/acoustic-grand-piano.html)

Downloaded from the "Salamander Grand Piano" section

File entry in the site -> "1.18GiB Best quality. 48kHz 24bit samples"

Original author of the audio recording files, Alexander Holm.

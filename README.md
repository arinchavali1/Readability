# Readability
Code for CS50's readability code 

#include <cs50.h>
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <math.h>

int main(void)
{
    string sentence = get_string("Enter Sentence: ");
    //index = 0.0588 * L - 0.296 * S - 15.8
    // L is number of letters per 100 words of text
    // S is avg # of sentences per 100 words of text
    // words can be defined as each space ' '
    // hello my name is arin --> this has 4 spaces and 5 words, meaning that spaces + 1 = words


    // we have asked for a sentence

     int count = 0; // setting a counter variable to count spaces in a sentence to determine word count
     int length = strlen(sentence); // integer length is equalized to the string length of the sentence given by user

    int i = strlen(sentence); // we initialize variable I to be the length of the string "Sentence" which is used to get the user to type a sentence
    int letters = 0;
    int words = 1; // words is initialized as 1 rather than 0 in order to account for the last word
    int sentences = 0;


    for (int x = 0; x < i; x++ ) // we use this for loop so the code goes from the start to the beginning to look all over the user inputted text for letters
    {
        char c = sentence[x];
        if (isalpha(c) != 0) // we use the isalpha function (checks string for alphabets)
        {
            letters++;
        }

        if(c == ' ') // spaces are used to determine how many words
        {
            words++;
        }

        if(c == '.' || c == '?' || c == '!') // we say if c = any puncuation marks that indicate a sentence ends, then the counter variable sentence adds 1;
        {
            sentences++;
        }
    }

    // after the for loop for counting, we have to set the equation.



    float L = ((float)letters / (float)words) * 100;
    float s = ((float)sentences / (float)words) * 100;
    float index = 0.0588 * L - 0.296 * s - 15.8;
    int rounded_index = round(index);
    if (rounded_index > 16)
    {
        printf("Grade 16+\n");
    }
    else if (rounded_index < 1)
    {
        printf("Before Grade 1\n");
    }
    else
    {
        printf("Grade %i\n", rounded_index);
    }














}


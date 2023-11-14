# Shuffle-game.cpp
#include <iostream>
#include <algorithm>
#include <ctime>

using namespace std;

int main()
{
    string originalWords[] = {"cake", "shotgun", "callofduty", "romantic", "damon"};
    string shuffledWords[] = {"cake", "shotgun", "callofduty", "romantic", "damon"};
    int level = 1;
    int lives = 5;
    int totalLevels = 5;

    srand(1234);

    for (string& word : shuffledWords) {
        random_shuffle(word.begin(),word.end());
    }

    while (level <= 5 && lives > 0) {
        string userInput;
        cout<<"Welcome to the guess the word game by JJ"<<endl;
        cout<<"The rules are simple you will given words to shuffle"<<endl;
        cout<<"Each words you fail you have to try again till you get it"<<endl;
        cout << "Level:" << level <<":Lives:" << lives <<endl;
        cout << "Shuffle the word:" << shuffledWords[level -1] <<endl;
        cout << "Enter your guess:";
        cin >> userInput;

        if (userInput == originalWords[level -1]) {
            cout << "Correct guess! moving to the next level." <<endl;
            ++level ;
        }
        else {
            cout << "Wrong guess! try again" <<endl;
            lives--;
        }
    }

    if (lives == 0){
        cout <<"Game over. you ran out of lives." <<endl;
        cout <<"do you want to play again(Y/N):"<<endl;


    }
    else{
        cout << "Congratulations! level completed." <<endl;
        }

    return 0;
}

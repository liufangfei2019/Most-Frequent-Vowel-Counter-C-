#include <iostream>
#include <map>
#include <string>
using namespace std;

int main() {
    string word;
    cin >> word;

    map<char, int> vowel_counts;
    string vowels = "aeiou";

    // Initialize map with vowels at 0
    for (char v : vowels) {
        vowel_counts[v] = 0;
    }

    // Count vowel occurrences
    for (char c : word) {
        if (vowel_counts.count(c)) {
            vowel_counts[c]++;
        }
    }

    // Find the most frequent vowel
    char most = 'a';
    int max_count = 0;

    for (auto [vowel, count] : vowel_counts) {
        if (count > max_count) {
            max_count = count;
            most = vowel;
        }
    }

    cout << "The most prominent vowel in your word was: '" 
         << most << "', appearing " << max_count << " times." << endl;

    return 0;
}


# Word-Count-in-text
from collections import Counter

def word_count(text):
    # Normalize the text: remove punctuation and convert to lower case
    normalized_text = ''.join(char for char in text if char.isalnum() or char.isspace()).lower()
    
    # Split the text into words
    words = normalized_text.split()
    
    # Calculate total word count
    total_word_count = len(words)
    
    # Count occurrences of each word
    word_counts = Counter(words)
    
    # Identify repeated words
    repeated_words = {word: count for word, count in word_counts.items() if count > 1}
    
    return total_word_count, word_counts, repeated_words

if __name__ == "__main__":
    # Get input from the user
    text = input("Please type your text: ")
    
    total_count, counts, repeats = word_count(text)
    
    print(f"\nTotal Word Count: {total_count}")
    print("\nWord Counts:")
    for word, count in counts.items():
        print(f"{word}: {count}")
    
    print("\nRepeated Words:")
    for word, count in repeats.items():
        print(f"{word}: {count}")

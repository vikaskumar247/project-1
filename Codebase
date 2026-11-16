import string


def analyze_text(text):

    # Convert text into lowercase and remove extra spaces
    text = text.strip().lower()

    # Count characters including spaces
    characters = len(text)

    # Count sentences
    sentences = 0

    for mark in ".!?":
        sentences += text.count(mark)

    # If text has no sentence-ending mark, count it as one sentence
    if sentences == 0 and text:
        sentences = 1

    # Remove punctuation using replace()
    for mark in string.punctuation:
        text = text.replace(mark, "")

    # Split text into words
    words = text.split()

    # Count total words
    total_words = len(words)

    # Count frequency using dictionary
    frequency = {}

    for word in words:
        if word in frequency:
            frequency[word] += 1
        else:
            frequency[word] = 1

    # Find unique words using set
    unique_words = set(words)

    # Sort words by frequency
    sorted_words = sorted(
        frequency,
        key=lambda word: (-frequency[word], word)
    )

    print("----- TEXT ANALYSIS -----")
    print("Words:", total_words)
    print("Characters (with spaces):", characters)
    print("Sentences:", sentences)
    print("Unique words:", len(unique_words))

    print("Word Frequency:")

    for word in sorted_words:
        print(word + ":", frequency[word])

    print("Unique Words (sorted by frequency):")

    for word in sorted_words:
        print(word)


def main():

    print("WELCOME TO WORD COUNTER & TEXT ANALYZER")

    print("Choose an option:")
    print("1. Enter text")
    print("2. Read text from a file")

    choice = input("\nEnter your choice: ").strip()

    if choice == "1":

        text = input("Enter your text: ")

        if not text.strip():
            print("No text to analyse.")
            return

    elif choice == "2":

        filename = input("Enter file name: ").strip()

        try:
            with open(filename, "r", encoding="utf-8") as file:
                text = file.read()

            if not text.strip():
                print("No text to analyse.")
                return

        except FileNotFoundError:
            print(f"File '{filename}' not found.")
            return

    else:
        print("Invalid option. Please choose 1 or 2.")
        return

    # Show analysis menu
    print("1. Full Text Analysis")
    print("2. Frequency Analysis")

    option = input("Choose analysis option: ").strip()

    if option == "1":
        analyze_text(text)

    elif option == "2":
        analyze_text(text)

    else:
        print("Invalid analysis option.")


if __name__ == "__main__":
    main()

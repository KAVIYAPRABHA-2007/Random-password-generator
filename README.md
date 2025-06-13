
import random
import string

def generate_password(length=12):
    if length < 4:
        return "Password length should be at least 4"

    # Define character sets
    uppercase_letters = string.ascii_uppercase
    lowercase_letters = string.ascii_lowercase
    digits = string.digits
    symbols = string.punctuation

    # Ensure at least one character from each set
    password = [
        random.choice(uppercase_letters),
        random.choice(lowercase_letters),
        random.choice(digits),
        random.choice(symbols)
    ]

    # Fill the rest with a mix of all characters
    all_characters = uppercase_letters + lowercase_letters + digits + symbols
    password += random.choices(all_characters, k=length - 4)

    # Shuffle the list to avoid predictable pattern
    random.shuffle(password)

    return ''.join(password)

# Example usage:
print("Generated Password:", generate_password(12))

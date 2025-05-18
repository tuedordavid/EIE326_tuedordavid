#def caesar_cipher(text, shift):
    """
    Encrypts the input text using a Caesar cipher with the specified shift.

    Args:
        text (str): The string to encrypt.
        shift (int): The number of places to shift each letter.

    Returns:
        str: The encrypted string.
    """
    result = []

    for char in text:
        if char.isupper():
            # Shift uppercase characters in the range A-Z
            shifted = chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
            result.append(shifted)
        elif char.islower():
            # Shift lowercase characters in the range a-z
            shifted = chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
            result.append(shifted)
        else:
            # Non-alphabetical characters remain unchanged
            result.append(char)

    return ''.join(result)

if __name__ == "__main__":
    plain_text = input("Enter text to encrypt: ")
    shift = int(input("Enter shift value (integer): "))
    encrypted_text = caesar_cipher(plain_text, shift)
    print(f"Encrypted text: {encrypted_text}")

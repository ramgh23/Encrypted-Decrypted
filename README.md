# Encrypted-Decrypted
Python code to get plain text from cipher text 

def decrypt(text, shift):
    decrypted_text = ""
    for char in text:
        if char.isalpha():  # Check if the character is a letter
            if char.islower():
                decrypted_text += chr((ord(char) - ord('a') - shift) % 26 + ord('a'))
            elif char.isupper():
                decrypted_text += chr((ord(char) - ord('A') - shift) % 26 + ord('A'))
        else:
            decrypted_text += char
    return decrypted_text

# Prompt the user to enter encrypted text and shift value
encrypted_text = input("Enter the encrypted text: ")
shift = int(input("Enter the shift value: "))

# Decrypt the encrypted text
decrypted_text = decrypt(encrypted_text, shift)

# Print the decrypted text
print("Decrypted text:", decrypted_text)

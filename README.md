def caesar_cipher_encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():  # Check if the character is a letter
            shifted = ord(char) + shift
            if char.islower():
                if shifted > ord('z'):
                    shifted -= 26
                elif shifted < ord('a'):
                    shifted += 26
            elif char.isupper():
                if shifted > ord('Z'):
                    shifted -= 26
                elif shifted < ord('A'):
                    shifted += 26
            encrypted_text += chr(shifted)
        else:
            encrypted_text += char  # Non-alphabetic characters remain unchanged
    return encrypted_text

def caesar_cipher_decrypt(text, shift):
    return caesar_cipher_encrypt(text, -shift)  # Decryption is just encryption with negative shift

# Example usage:
plaintext = "Hello, World!"
shift_amount = 3

encrypted_text = caesar_cipher_encrypt(plaintext, shift_amount)
print("Encrypted:", encrypted_text)

decrypted_text = caesar_cipher_decrypt(encrypted_text, shift_amount)
print("Decrypted:", decrypted_text)

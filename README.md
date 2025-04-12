def caesar_encrypt(text, shift):
    encrypted = ""
    for char in text:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            encrypted += chr((ord(char) - base + shift) % 26 + base)
        else:
            encrypted += char
    return encrypted

def caesar_decrypt(cipher, shift):
    return caesar_encrypt(cipher, -shift)
plain_text = "Hello, World!"
shift_amount = 3

cipher_text = caesar_encrypt(plain_text, shift_amount)
print("Encrypted:", cipher_text)

decrypted_text = caesar_decrypt(cipher_text, shift_amount)
print("Decrypted:", decrypted_text)

import re

def validate_username(username):
    # 5–15 characters, letters and numbers only
    return re.fullmatch(r"[A-Za-z0-9]{5,15}", username) is not None

def validate_password(password):
    # At least 8 characters
    # At least 1 uppercase, 1 lowercase, 1 number
    pattern = r"^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$"
    return re.fullmatch(pattern, password) is not None

username = input("Enter username: ")
password = input("Enter password: ")

if validate_username(username) and validate_password(password):
    print("Input is valid ✅")
else:
    print("Invalid input ❌")

import string

password = input("Enter your password: ")

score = 0

# Check length
if len(password) >= 8:
    score += 1

# Check uppercase
if any(char.isupper() for char in password):
    score += 1

# Check lowercase
if any(char.islower() for char in password):
    score += 1

# Check numbers
if any(char.isdigit() for char in password):
    score += 1

# Check special characters
if any(char in string.punctuation for char in password):
    score += 1


# Display result
print("\nPassword Strength:")

if score <= 2:
    print("Weak Password ❌")
    print("Suggestion: Use at least 8 characters with uppercase, lowercase, numbers and special characters.")

elif score == 3 or score == 4:
    print("Medium Password ⚠️")
    print("Suggestion: Add more complexity to make your password stronger.")

else:
    print("Strong Password ✅")
    print("Your password has good complexity.")

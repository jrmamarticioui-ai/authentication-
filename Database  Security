import sqlite3
import bcrypt

try:
    # Connect to database
    conn = sqlite3.connect("users.db")
    cursor = conn.cursor()

    # Create table if not exists
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS users (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            username TEXT UNIQUE NOT NULL,
            password BLOB NOT NULL
        )
    """)

    # ---- Register User ----
    username = input("Enter username: ")
    password = input("Enter password: ").encode('utf-8')

    # Hash password
    hashed_password = bcrypt.hashpw(password, bcrypt.gensalt())

    # Parameterized query (prevents SQL injection)
    cursor.execute(
        "INSERT INTO users (username, password) VALUES (?, ?)",
        (username, hashed_password)
    )

    conn.commit()
    print("User registered successfully ✅")

except sqlite3.IntegrityError:
    print("Username already exists ❌")

except Exception as e:
    print("Error:", e)

finally:
    conn.close()

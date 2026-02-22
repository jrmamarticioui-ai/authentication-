import os
import sqlite3
from dotenv import load_dotenv

try:
    # Load environment variables from .env file
    load_dotenv()

    # Read environment variables
    DB_NAME = os.getenv("DB_NAME")
    DB_PASSWORD = os.getenv("DB_PASSWORD")

    # Validate environment variables
    if not DB_NAME or not DB_PASSWORD:
        raise ValueError("Environment variables not set properly.")

    # Connect to database using env configuration
    conn = sqlite3.connect(DB_NAME)
    cursor = conn.cursor()

    cursor.execute("CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY)")
    conn.commit()

    print("Environment configured securely ✅")

except Exception as e:
    print("Configuration Error:", e)

finally:
    try:
        conn.close()
    except:
        pass

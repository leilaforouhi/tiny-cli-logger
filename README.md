
#!/usr/bin/env python3
"""
Tiny CLI Logger
- Logs current date/time and basic environment details into log.txt
"""

import datetime, platform, os

def main():
    now = datetime.datetime.now().isoformat(timespec="seconds")
    info = {
        "timestamp": now,
        "os": platform.system(),
        "release": platform.release(),
        "python": platform.python_version(),
        "cwd": os.getcwd(),
    }

    line = " | ".join(f"{k}={v}" for k, v in info.items())
    with open("log.txt", "a", encoding="utf-8") as f:
        f.write(line + "\n")

    print("Log entry added:", line)

if __name__ == "__main__":
    main()

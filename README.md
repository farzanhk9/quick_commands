import os
import webbrowser

# ⚡ Quick Command Launcher
commands = {
    "google": lambda: webbrowser.open("https://www.google.com"),
    "youtube": lambda: webbrowser.open("https://www.youtube.com"),
    "github": lambda: webbrowser.open("https://github.com"),
    "shop": lambda: webbrowser.open("https://www.amazon.com"),
    "open_folder": lambda: os.startfile("C:\\Users"),  # Change path if needed
    "notepad": lambda: os.system("notepad"),
    "calc": lambda: os.system("calc"),
}

def main():
    print("⚡ Quick Command Tool")
    print("======================")
    print("Available commands:", ", ".join(commands.keys()))

    while True:
        cmd = input("\n👉 Enter command (or 'exit' to quit): ").lower().strip()
        if cmd == "exit":
            print("👋 Goodbye!")
            break
        elif cmd in commands:
            try:
                commands[cmd]()
                print(f"✅ Command '{cmd}' executed!")
            except Exception as e:
                print(f"⚠️ Error: {e}")
        else:
            print("❌ Unknown command!")

if __name__ == "__main__":
    main()

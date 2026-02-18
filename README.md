By Qwen
<a href="https://afnan-nex.github.io/n8n-variable-code-maker/code-to-file-creator_qwen.html" target="_blank" rel="noopener noreferrer">Qwen</a>

By Manus
<a href="https://afnan-nex.github.io/n8n-variable-code-maker/code-to-file-creator_manus.html" target="_blank" rel="noopener noreferrer">Manus</a>

# **n8n-anycode-runner**

A web-based tool designed to simplify the process of creating and running code files for [n8n](https://n8n.io/) automation workflows. 

* It can generate script everytime(new) for/with **variables** in n8n

With this tool, you can input any type of code (e.g., Python, CMD, JavaScript, or others), specify a file path, and generate a Windows CMD command to create the file.

## **Features**

*   **Code Input**: Paste any code (Python, JavaScript, CMD, etc.) into a user-friendly textarea.
*   **File Path Specification**: Define the full file path, including filename and extension (e.g., `C:\Users\Admin\Downloads\script.py`).
*   **CMD Command Generation**: Automatically generates a Windows CMD command to create the specified file with your code.
*   **Copy to Clipboard**: Easily copy the generated CMD command for use in n8n workflows or elsewhere.
*   **Clear Functionality**: Reset all inputs and outputs with a single click.
*   **Responsive Design**: Works seamlessly on both desktop and mobile devices.
*   **Keyboard Shortcuts**: Use `Ctrl+Enter` to generate the command and `Ctrl+C` to copy the output when focused on the output area.
*   **Auto-Generation**: Automatically updates the CMD command as you type (with a 500ms debounce).

## **Getting Started**

### **Prerequisites**

*   A modern web browser (e.g., Chrome, Firefox, Edge).
*   No additional software or dependencies are required, as this is a fully client-side web application.

### **Usage**

1.  Open the `code-to-file-creator.html` file in your browser.
2.  Paste your code into the "Your Code" textarea.
3.  Enter the desired file path, including the filename and extension, in the "File Path + Name + Extension" input field (e.g., `C:\Users\Admin\Downloads\script.py`).
4.  Click the **Generate CMD Command** button or press `Ctrl+Enter` to create the Windows CMD command.
5.  The generated command will appear in the "CMD Command Output" textarea.
6.  Click the **Copy Output** button or press `Ctrl+C` (when focused on the output) to copy the command to your clipboard.
7.  Use the copied command in your n8n workflow or run it directly in a Windows Command Prompt.
8.  Click the **Clear All** button to reset the inputs and output.

### **Example**

#### **Input Code**
```
import telebot
# Replace with your actual bot token
TOKEN = 'YOUR_BOT_TOKEN_HERE'
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(func=lambda message: True)
def save_message_to_file(message):
    if message.text:
        try:
            with open("message.txt", "w", encoding="utf-8") as file:
                file.write(message.text)
            bot.send_message(message.chat.id, "Message saved to file.")
        except Exception as e:
            bot.send_message(message.chat.id, f"Error saving message: {str(e)}")
    else:
        bot.send_message(message.chat.id, "Only text messages are supported.")

if __name__ == "__main__":
    print("Bot is running...")
    bot.infinity_polling()
```
#### **File Path**
```
C:\Users\Admin\Downloads\telegram_bot.py
```
#### **Generated CMD Command**
```
echo import telebot> "C:\Users\Admin\Downloads\telegram_bot.py" & echo # Replace with your actual bot token>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo TOKEN = 'YOUR_BOT_TOKEN_HERE'>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo bot = telebot.TeleBot(TOKEN)>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo.>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo @bot.message_handler(func=lambda message: True)>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo def save_message_to_file(message):>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo     if message.text:>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo         try:>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo             with open(^"message.txt^", ^"w^", encoding=^"utf-8^") as file:>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo                 file.write(message.text)>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo             bot.send_message(message.chat.id, ^"Message saved to file.^")>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo         except Exception as e:>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo             bot.send_message(message.chat.id, f^"Error saving message: {str(e)}^")>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo     else:>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo         bot.send_message(message.chat.id, ^"Only text messages are supported.^")>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo.>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo if __name__ == ^"__main__^":>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo     print(^"Bot is running...^")>> "C:\Users\Admin\Downloads\telegram_bot.py" & echo     bot.infinity_polling()>> "C:\Users\Admin\Downloads\telegram_bot.py"
```
This command can be used in an n8n workflow to create a `telegram_bot.py` file with the provided code.

## **Installation**

Clone this repository:  
```
git clone https://github.com/afnan-nex/n8n-anycode-runner
```
1.  Open the `code-to-file-creator.html` file in your preferred web browser.
2.  Start using the tool!

## **License**

This project is licensed under the MIT License. See the [LICENSE](https://grok.com/chat/LICENSE) file for details.

© 2025 Afnan Siddiqui

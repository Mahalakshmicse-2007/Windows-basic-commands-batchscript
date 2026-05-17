# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
<img width="353" height="92" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM" src="https://github.com/user-attachments/assets/fdd31530-ad1f-483c-be8d-e83b6f3addfa" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
<img width="306" height="80" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (1)" src="https://github.com/user-attachments/assets/b1e1c614-2739-4ee1-a771-ce31afe586ce" />

Create the file Rose.txt

## COMMAND AND OUTPUT
<img width="367" height="101" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (5)" src="https://github.com/user-attachments/assets/e57934f4-fc7b-4dc3-934a-c3d5ad65a3e8" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
<img width="453" height="92" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (3)" src="https://github.com/user-attachments/assets/03658c96-6b28-4d62-939e-e44644a9bb8c" />

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
<img width="459" height="104" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (4)" src="https://github.com/user-attachments/assets/a2b3e6d8-d469-4501-95ff-bf87d86673e9" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
<img width="367" height="101" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (5)" src="https://github.com/user-attachments/assets/ad785a36-2d42-4e3d-adc8-b85c687d886c" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
<img width="430" height="188" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (6)" src="https://github.com/user-attachments/assets/ca3da007-381c-4aca-873e-f5380184a6a4" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
<img width="392" height="221" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (7)" src="https://github.com/user-attachments/assets/2d499a74-fcb7-41f5-ab0c-dab34e1f64de" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
<img width="399" height="142" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (8)" src="https://github.com/user-attachments/assets/c728503b-7d4d-407b-9635-1b3b25682caf" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
PROGRAM

@echo off set name=John echo Hello, %name% pause

## OUTPUT
<img width="389" height="134" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (9)" src="https://github.com/user-attachments/assets/690be44a-3945-4325-b6f2-9b754210c425" />

Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
PROGRAM

@echo off

:START

set /p num=Enter a number:

set /a rem=%num% %% 2

if %rem%==0 ( echo The number is Even ) else ( echo The number is Odd )

set /p choice=Do you want to continue (Y/N)?

if /I "%choice%"=="Y" goto START if /I "%choice%"=="N" goto END

echo Invalid Input goto START

:END echo Thank You pause

## OUTPUT
<img width="469" height="202" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (10)" src="https://github.com/user-attachments/assets/0f338061-0518-47b1-89a4-487c1b5daa56" />

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

PROGRAM

@echo off

for /L %%i in (1,1,5) do ( echo Number: %%i )

pause

## OUTPUT
<img width="358" height="158" alt="WhatsApp Image 2026-05-16 at 2 53 17 PM (11)" src="https://github.com/user-attachments/assets/80c93cd9-f95f-41f4-87f6-2a54a44859ea" />

Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
PROGRAM

@echo off

if exist sample.txt ( echo sample.txt exists ) else ( echo sample.txt does not exist )

pause

## OUTPUT
<img width="394" height="89" alt="WhatsApp Image 2026-05-16 at 2 53 18 PM" src="https://github.com/user-attachments/assets/bbef36ae-6877-4b19-bf4a-dcdddecdb230" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
PROGRAM @echo off

:MENU echo ==================== echo 1. Say Hello echo 2. Create a File echo 3. Exit echo ====================

set /p choice=Enter your choice:

if %choice%==1 goto HELLO if %choice%==2 goto CREATE if %choice%==3 goto EXIT

echo Invalid Choice goto MENU

:HELLO echo Hello, World! pause goto MENU

:CREATE echo This is a new file > newfile.txt echo File Created pause goto MENU

:EXIT echo Goodbye pause exit


## OUTPUT
<img width="485" height="184" alt="WhatsApp Image 2026-05-16 at 2 53 18 PM (1)" src="https://github.com/user-attachments/assets/6e0a41e6-b029-4348-b04d-92b82b8d190c" />

# RESULT:
The commands/batch files are executed successfully.


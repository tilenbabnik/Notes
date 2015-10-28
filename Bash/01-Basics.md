cd locationName # Change Directory
pwd # Print working directory
ls # Lists all files and folders
ls -l # Lists all files and folders with more options
ls -a # Shows also hidden folders
mkdir folderName  # Creates new folder
touch fileName  # Creates new file
rm fileName  # Removes the file
rm -rf  # Removes the folder
mv sourceName targetName # Moves folder or file to specified folder
mv sourceName1 sourceName2 targetName # Moves multiple files to specified folder
mv name1.html name2.html  # Renames the file
* # Selects all files
../ # One directory up
*.ext # Selects all ext files
cp sourceName targetName  # Copies the file

echo "Hello World"  # Outputs Hello world on screen
echo "Hello" > hello.txt  # Output Hello to hello.txt
cat hello.txt # Reads hello.txt and ouputs content on screen
cat rivers.txt > water.txt  # Puts content of rivers.txt to water.txt
cat rivers.txt >> oceans.txt  # Appends content of rivers.txt to oceans.txt
cat < volcanoes.txt # Inputs content of volcanoes.txt to terminal
cat volcanoes.txt | wc  # Pipes left command to the one on the right.
cat lakes.txt | sort > sorted-lakes.txt # Sorts content from lakes.txt and outputs to sorted-lakes.txt
sort  # Sorts content
uniq  # Removes duplicate lines that follow one another
grep Mount mountains.txt  # Searches mountains.txt for matches and prints matching lines
grep -r Arctic /Urban/Documents/School  # Searches the whole directory
sed 's/snow/rain/g' forests.txt # sed searches forests.txt and replaces every 'snow' with 'rain'

nano hello.txt  # Opens text editor inside terminal
Ctrl + O  # Saves the edited file
Ctrl + X  # Closes the nano editor

git config --global alias.co checkout

Ctrl + U: Clears the line from the cursor point back to the beginning.
Ctrl + A: Moves the cursor to the beginning of the line.
Ctrl + E: Moves the cursor to the end of the line.
Ctrl + R: Allows you to search through the previous commands.
Ctrl + C: Stop running tasks

Command + K: Clears the console screen

open ~/.bash_profile = opens the file to store settings

echo "Urban je car" = Will output this string on opening of terminal
alias awesome="cd ~/Desktop/Rails/Readit" = saves the command after = to the word awesome

export urban="Urbi legendex" = Saves the string to variable urban
echo $urban = To access the variable use $

export PS1="" = Changing the prompt
export USER="Urban Cvek" = Changing the current user
env = prints the current enviroment variables

git init
git status
git add .
git commit -m "Commit message" # Write commit messages in present tense
git remote add $remoteName ssh@url
git push

git checkout $branchName
git merge $branchName
git branch -d $branchName
git branch -D $branchName # if you screw up and don't want to merge

git checkout -b $branchName
git checkout $branchName
git branch

git fetch
git pull

git config --global user.name "Your Name"
git config --global user.email your.email@example.com
git config --global push.default matching

git config --global alias.co checkout
git config --global alias.s status

git log

git checkout -f

cat ~/.ssh/id_rsa.pub

mono tj.exe Program.java testi rezultati

mono tj.exe Program.java . .

i=1;while [ 1 ];do screencapture -t jpg -x ~/Desktop/screencapture/Snemanje1/$i.jpg; let i++;sleep 1; done

find ~/Bedno  -type f -exec cp {} ~/Desktop/Test \;

https://github.com/gaganpreet/udemy-dl is a Git repository.

udemy-dl https://www.udemy.com/COURSE_NAME

-u urbancvek@cunomo.com
-p Hitriurbi1
-o /path/to/directory/

--help

udemy-dl -u urbancvek@cunomo.com -p Hitriurbi1
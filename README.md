Bash 

Here you can find some bash commands that I used to do tasks during my QA studies.

### Working with files and directories
```bash
cd                                                                # Home dirrectory
pwd                                                               # Show current directory path
mkdir test1                                                       # Create a directory named test1
cd test1                                                          # Go to directory test1 (also possible to write the path to needed directory)
touch {1..3}.txt                                                  # Create file 1,2 and 3 inside directory test1
ls                                                                # Check directory test1 content (ls -la if there are any hidden files)
cd                                                                # Go home directory
mkdir test2                                                       # Create directory test2 inside home directory
rmdir test2                                                       # Delete directory test2 
rm test1/2.txt                                                    # Delete file 2
mkdir test3 touch test3/{1..2}.txt                                # Create dirrectory test3 and add two files to directory test3
rm -rf test3                                                      # Delete directory test3       
mkdir test4                                                       # Create directory test4
mv test1/[1,3].txt test4                                          # Move file1.txt and file3.txt from directory test1 to directory test4
echo -e  "line\nline\nline" >> test4/1.txt                        # Add 3 lines to file1.txt
cat test4/1.txt                                                   # Print content of file1.txt
echo -e  "line\nline\nline" >> test4/3.txt                        # Add 3 lines to file3.txt
cat test4/[1,3].txt                                               # Print contents of file1.txt and file3.txt at once
nano test4/1.txt                                                  # Using one of the editors, replace all lines in file1.txt and file3.txt
nano editor is displayed
press "ctrl+\" for searhing and type "line", then press enter
type alt text, for instance: "new line", then press enter
press "A" to affect all rows
press "Ctrl+x" to exit nano editor
press "Y" to save modified bufer
press "Enter" to confirm file name
```

### Editing files, checking and killing proccesses, pinging websites
```bash
cd                                                                # Home dirrectory
mkdir test3                                                       # Create directory test3
echo -e "row1\nrow2\nrow3\nrow4" | tee test3/{4..6}.txt           # Add 3 files to test3, each of which should contain 4 rows
grep "row2" test3/5.txt                                           # Find the line "row2" in file5.txt
grep -R "row2" test3                                              # Find the line "row" in the test3 directory
grep -w "row" -c -v  test3/6.txt                                  # Count number of lines containing word "row" in file6.txt
find test3  -name "5.txt"                                         # Find file 5.txt in test3 directory
find -name "5.txt" -delete                                        # Delete file5.txt using find command 
echo "test" >> test3/4.txt                                        # Add the word "test" to file4.txt using the echo command 
sed -i "s/test/fail/gi" test3/4.txt                               # Change the word "test" in file4.txt to "fail"
echo "test" >> test3/4.txt                                        # Add the word "test" to file4.txt so that the content is preserved
ps aux                                                            # View all processes in the system
kill 666                                                          # Kill process 666 in console
ping artsiomrusau.com                                             # Check the availability of the website artsiomrusau.com using ping
ping -c 5 artsiomrusau.com                                        # Send 5 packages to artsiomrusau.com  
curl https://petstore.swagger.io/v2/pet/                          # Using GET and cURL command, get info about registered pets at petstore.swagger.io
findByStatus?status=available                                    
curl -X POST https://petstore.swagger.io/v2/user/createUser       # Using POST and cURL command, create a new user at petstore.swagger.io
--data "id=55"
--data "username=Paul"
--data "firstName=Paul"
--data "lastName=Willon"
--data "email=eee@ee.com"
--data "password=aabbccdd"
--data "phone=9920040506"
--data "userStatus=11" 
```
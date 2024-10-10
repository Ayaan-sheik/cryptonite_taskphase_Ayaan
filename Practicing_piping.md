# Practicing Piping

## Redirecting Output

This > will redirect the output of the command before > to the next argument or command after the > like 

`echo hi > asdf` 

similarly in the challenge 

- commands used:
    - echo PWN > COLLEGE
- flag: pwn.college{M62q9VrWNFIt5PiiWRs4M5Iwojv.dRjN1QDL4QDO1czW}

## Redirecting more output

In this challenge we cant directly print the flag by running /challenge/run we instead need to redirect this to the file myflag. then use cat function to retrieve the flag from the myflag file

- commands used:
    - /challenge/run > myflag
    - cat myflag
- flag: pwn.college{0SYUNrFa-OOBWXNkGVkTAszGqI1.dVjN1QDL4QDO1czW}

## Appending output

append mode redirect is done by >>  in this challenge we are trying  to append the secodn half of the flag by appending using the /challenge/run by redirecting the output to /home/hacker/the-flag

- commands used:
    - /challenge/run >> /home/hacker/the-flag
    - cat /home/hacker/the-flag
- flag: pwn.college{gvf3sKPgrH9cbcyknx5B9BYYInJ.ddDM5QDL4QDO1czW}

## Redirecting errors

In linux there are error channel of commands . We learn about file descriptor(FD) its a number that describes communication channels.  FD 0: standard input FD 1: standard output FD 2: Standard errors. some fd numbers are implicit like > means 1> .

In this challenge we need to redirect errors from /challenge/run to errors.log and output to myflag then retrieve flag from myflag.

- commands used:
    - /challenge/run 2> instructions > myflag
    - cat myflag
- flag :pwn.college{guE1nOLHE03eLj4dGVWWGCRBiuh.ddjN1QDL4QDO1czW}

## Redirecting input

just like we can redirect output we can redirect input to commands. In this challenge we need to redirect the word College that is in the file PWN to the command /challenge/run.

- commands used:
    - /challenge/run < PWN
- flag: pwn.college{QsKwkiKp_WP9KYMKY4fumXqeXWW.dBzN1QDL4QDO1czW}

## Grepping stored results

we are using grepping and redirecting together to fidn the flag in the txt file 

- commands used:
    - /challenge/run > /tmp/data.txt
    - grep pwn.college /tmp/data.txt
- flag: pwn.college{IRhR9G1q0Mhl6i7KQQ6BItEsCTC.dhTM4QDL4QDO1czW}

## Grepping live output

in the previous challenge we are storing the output in a file thn we are grepping the flag out of it we can cut the putting the data into the file by using the pipe command .

- commands used:
    - /challenge/run | grep pwn.college
- flag:pwn.college{Y0jYNNY-rwg_OqEa3eEAx3nboEa.dlTM4QDL4QDO1czW}

## Grepping errors

we can grep errors by converting the the errors to standard output thn using the | command to use the grep command to find the flag and output it. we are using 2>&1 .

- commands used :
    - /challenge/run 2>& 1 |grep pwn.college
- flag: pwn.college{Icyx0062Hvw6PIOOaH8SY_oGe_B.dVDM5QDL4QDO1czW}

## Duplicating piped data with tee

the tee command duplicates the piped data . this is used as when piping we cant see the output so when we run into error tee helps us easy to depug. in the challenge the first command shoudl be piped into the second command but a argument is missing to debug this we will use tee 

- commands used:
    - /challenge/pwn | tee cmd_o | /challenge/college
    - cat cmd_o
    - /challenge/pwn --secret oZ5GaGk8 | tee cmd_o | /challenge/college
- flag: pwn.college{oZ5GaGk85lNQrN9g3sxHxNUsU59.dFjM5QDL4QDO1czW}

## Writing to multiple programs

We can use tee to write output into two files or one file one command but to write it into two commands we need to use smthng called process substitution. ( >(rev) ) here rev is a cmd.

- commands used:
    - /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
- flag: pwn.college{ETqcZdvNSWzsgUmhlzpxIQfhK3X.dBDO0UDL4QDO1czW}

## split piping stderr and stdout

in this challenge we are combining all the redirection and piping functions . in this challenge we need to redirect the stderr to one  file anf edoutput to another.

- commands used:
    - /challenge/hack 2> >(/challenge/the) > >(/challenge/planet)
- flag:pwn.college{IfEEzU1QpvlEQuu5wtQHJ081Pao.dFDNwYDL4QDO1czW}

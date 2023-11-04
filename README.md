# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE
# Aim:
write C programs to illustrate IPC using pipes mechanisms

# Algorithm: IPC using pipes

Create a child process usingfork()

Create a simple pipe with C, we make use of the pipe() systemcall.

Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting

Close the read end of parent process using close() and perform writeoperation

Close the write end of child process and performreading

Display thetext.

## PROGRAM:
```C
#include <stdio.h>
int main()
{

  int fd[2],child; char a[10];
  printf("\nEnter the string : ");
  scanf("%s",a);
  pipe(fd);
  child=fork();
  if(!child)
{
    close(fd[0]);
    write(fd[1],a,5); wait(0);
}

  else

{
   close(fd[1]);
    read(fd[0],a,5); printf("The string received from pipe is : %s",a);
}

return 0;
}
```


# OUTPUT:
![Screenshot (3)](https://github.com/Rajkiran276/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/147471453/96cb319a-9dd0-4dfb-afdf-7cfb3c66924b)

# Result:
Thus, IPC using pipes mechanisms is illustrated using c program successfully

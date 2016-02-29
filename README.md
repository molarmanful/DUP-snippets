# [DUP](https://esolangs.org/wiki/DUP) Snippets
DUP is a great language as is. However, there are times when the current set of operators just isn't enough. DUP Snippets is about to change all that.
## Notes
All snippets are lambdas to allow you to adapt them to your needs. If you have any snippets you want to see in this collection, feel free to pull-request with your edits!

To get the most out of these snippets, you should be at least somewhat familiar with DUP already. If you aren't, don't worry; DUP is easy to learn.
## Let's start!
### Clear Stack
```
[[$][%]#]
```
### Stack Length
```
[1[$ø][1+]#1-]
```
### Stack to Array
```
[0[^][^^:\%1+]#]
```
Top of stack is set to `0`. Also leaves array length as top of stack.
### Array to Stack
```
[[1-$;$][\]#%%]
```
Assumes array length is top of stack.
### Reverse Stack
```
[0[^][^^:\%1+]#%0[$;$][\1+]#%%]
```
### Rotate Stack
This one takes bottom of stack and moves it to top of stack:
```
[0[^][^^:\%1+]#1-$l:1-[$;$][\1-]#%%l;;]
```
This one takes top of stack and moves it to bottom of stack:
```
[0[^][^^:\%1+]#0;[\1-$][$;]#%]
```
However, if you know how many items you want to rotate, the following snippets are much easier.

Rotating top 4 items:
```
[(@)\]
```
Rotating top 5 items:
```
[((@)\)\]
```
Rotating top 6 items:
```
[(((@)\)\)\]
```
See the pattern?
### Print String/Array
String:
```
[0[$;$][,1+]#%%]
```
Array (space-separated):
```
[[1-$;$][.' ,]#%%]
```
This assumes that array length is top of stack.
### Inclusive Range
```
[[^^<][^1+\]#%]
```
Takes 2 numbers and creates a range in their place.
### Stack Sum
Destructive version:
```
[[^][+]#]
```
Non-destructive version:
```
[0[^][^^:\%1+]#0\[1-$;$][@+\]#%%]
```
To get stack product, just replace the last `+` with `*`.
### Nth Power
```
[^a:[1-$][\a;*\]#%]
```
### Integer Square Root
```
[1[^^/\%^=~][1+]#]
```
### Get Entire Input
```
[[`$~][]#%]
```
### Bitwise Left Shift (`<<`)
```
[[$][\2*\1-]#%]
```
### Bitwise Right Shift (`>>`)
```
[[$][\2/\%\1-]#%]
```

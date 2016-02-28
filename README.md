# [DUP](https://esolangs.org/wiki/DUP) Snippets
DUP is a great language as is. However, there are times when the current set of operators just isn't enough. DUP Snippets is about to change all that.
## Notes
All snippets are lambdas to allow you to adapt them to your needs. If you have any snippets you want to see in this collection, feel free to pull-request with your edits!
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
Top of stack is set to `0`. Also leaves stack length as top of stack.
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

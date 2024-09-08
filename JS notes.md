#js 
# eval()
This is a function used to execute javascript as string.
- it can access variables in its own lexical environment (meaning outside of the eval function it can read data)
- [!] This is very dangerous as it is very exploitable
- if a minifier is used for compressing the js, eval can also access variables inside the compressed code
# Suffix Rules

Suffix rules are a more limited way to define implicit rules. Pattern rules are more general and clearer, but suffix rules are retained for compatibility. 


```
$ make -p  | grep -nA2 '%.o: %\.c$'
478:%.o: %.c
479-#  recipe to execute (built-in):
480-    $(COMPILE.c) $(OUTPUT_OPTION) $<

$ make -p | grep -nA2 '^.c.o:' 
997:.c.o:
998-#  Builtin rule
999-#  Implicit rule search has not been done.
```

The listed pattern rules are applied. The suffix rules are only listed but not used

The very short answer is: the suffix rules are defined because POSIX make requires them to be built-in. See the section named "Default Rules". The pattern rules are (non-POSIX) GNU value-add.

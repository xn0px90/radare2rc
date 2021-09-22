# .radare2rc
r2 rc 

------------------------------------------------------
```
# Show comments at right of disassembly
e asm.cmtright=true

# Shows pseudocode in disassembly. Eg mov eax, str.ok = > eax = str.ok
e asm.pseudo = true

#ESIL EMU 
e asm.emu=true
e asm.esil = true

# Display stack and register values on top of disasembly view (visual mode)
e cmd.stack = true

# Solarized theme
eco dark

# Use UTF-8 to show cool arrows that do not look like crap :)
e scr.utf8 = true

e asm.describe = true 

# Sanbox settings
e cfg.sandbox=false
```

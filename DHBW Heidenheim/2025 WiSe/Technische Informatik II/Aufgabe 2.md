```
.global _start

.section .text
_start:
    LDR r0, =Total   @ Adresse von Total Laden
    MOV r1, #0       @ Adresse für 0 laden
    LDR r2, =Table   @ Adresse für Table laden
    LDR r3, =Count   @ Count Adresse laden
    LDR r4, [r3]     @ Count Value laden
	
	CMP r4, #0       @ Compare Count to 0
    BEQ Exit          @ If Count is 0, skip loop
	
Loop:
    LDR r5, [r2], #4 @ Wert der Tabellen Adresse Laden und dann zur nächsten gehen
    ADD r1, r1, r5   @ Total Rechnen

    SUBS r4, r4, #1  @ Count Abziehen -> Falls Count negativ witd Flag setzen
    BGE Loop         @ Wenn negativ flag gesetzt dann loop abrechen

    STR r1, [r0]     @ Total Speichern

Exit:
    MOV r7, #1       @ syscall: exit
    MOV r0, #0       @ status 0 (success)
    SVC #0           @ make syscall

.section .data
Total:  .word 0
Count:  .word 5
Table:  .word 39, 25, 4, 98, 17
```
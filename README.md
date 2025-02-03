# Unexpected Behavior when Partially Clearing Alphanumeric Fields in COBOL

This example demonstrates a common, yet subtle, error in COBOL related to clearing alphanumeric fields.  When you attempt to clear only a portion of an alphanumeric field using `MOVE SPACE` with substring notation (e.g., `MOVE SPACE TO WS-AREA-1(1:1)`), only that specific part is cleared. The rest of the field retains its previous contents.  This can lead to unexpected results, especially if the code relies on the field being entirely empty.

The `bug.cob` file shows the problematic code.  `bugSolution.cob` presents a corrected version using `MOVE SPACE TO` on the entire field to ensure complete clearing.

This is a frequently overlooked detail. Always ensure that you completely clear your fields using appropriate methods if you intend to use the entire field later in your program.

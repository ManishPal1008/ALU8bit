# ALU8bit
An Arithmetic Logic Unit (ALU) is a fundamental component of a computer processor responsible for performing arithmetic (addition, subtraction, multiplication, division) and logical (AND, OR, NOT, XOR) operations on binary data. It takes input from memory or registers, processes the data according to the instructions provided by the control unit, and produces output results. ALUs are critical for executing mathematical calculations and logical operations necessary for computing tasks.
It has inputs operand_a and operand_b, each being 8 bits wide, representing the two operands for the ALU operations.
The input operation is 4 bits wide and specifies the operation to be performed.
The output result is 8 bits wide and represents the result of the ALU operation.
The output carry_out indicates whether there is a carry-out from the most significant bit during arithmetic operations.
Inside the module:

ALU_Result is an 8-bit register that holds the result of the ALU operation.
extended_result is a 9-bit wire used to compute the carry-out for addition operation by extending the operands by one bit to handle the potential carry-out.
result is assigned the value of ALU_Result.
carry_out is assigned the value of the most significant bit of extended_result.
The always block describes the behavior of the ALU based on the operation input:

Arithmetic operations (0000 to 0011): Addition, subtraction, multiplication, and division are performed between operand_a and operand_b.
Bitwise operations (0100 to 0111): Logical shift left, logical shift right, rotate left, and rotate right are performed on operand_a.
Logical operations (1000 to 1101): Logical AND, OR, XOR, NOR, NAND, and XNOR are performed between operand_a and operand_b.
Comparison operations (1110 and 1111): Greater than and equal comparison between operand_a and operand_b are performed.
If the operation does not match any of the specified cases, the default behavior is to ALU_Result = 8'bxxxx_xxxx; // don’t care(default case).

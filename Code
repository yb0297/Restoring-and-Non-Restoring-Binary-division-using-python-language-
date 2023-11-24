def restoring_division(dividend, divisor):
    # Check if the divisor is '00000000' (all 0s), which is not allowed
    if dividend == '00000000' or divisor == '00000000':
        raise ValueError("Division by zero is not allowed.")
    
    # Check if the dividend is '00000000', and if so, return '00000000' for quotient and remainder
    if dividend == '00000000':
        return '00000000', 0, '00000000', 0

    # Convert binary inputs to decimal integers
    dividend = int(dividend, 2)
    divisor = int(divisor, 2)

    # Initialize quotient to 00000000 and remainder to the decimal equivalent of the binary dividend
    quotient = 0
    remainder = dividend

    # Repeatedly subtract divisor from remainder until it's less than divisor
    while remainder >= divisor:
        remainder -= divisor
        quotient += 1

    # Convert results to 8-bit binary and return
    binary_quotient = format(quotient, '08b')
    binary_remainder = format(remainder, '08b')

    return binary_quotient, quotient, binary_remainder, remainder

# Function for Non-Restoring Division with 8-bit binary input
def non_restoring_division(dividend, divisor):
    # Check if the divisor is '00000000' (all 0s), which is not allowed
    if dividend == '00000000' or divisor == '00000000':
        raise ValueError("Division by zero is not allowed.")
    
    # Check if the dividend is '00000000', and if so, return '00000000' for quotient and remainder
    if dividend == '00000000':
        return '00000000', 0, '00000000', 0

    # Calculate the number of bits in the binary dividend
    bits = len(dividend)

    # Initialize quotient to 00000000 and remainder to 00000000
    quotient = 0
    remainder = 0

    # Loop through each bit in the 8-bit binary dividend
    for i in range(bits):
        # Shift both quotient and remainder to the left (multiply by 2)
        quotient <<= 1
        remainder <<= 1
        remainder |= int(dividend[i])

        # If remainder is greater than or equal to the decimal equivalent of the binary divisor, subtract it and set a bit in the quotient
        if remainder >= int(divisor, 2):
            remainder -= int(divisor, 2)
            quotient |= 1

    # Convert results to 8-bit binary and return
    binary_quotient = format(quotient, '08b')
    binary_remainder = format(remainder, '08b')

    return binary_quotient, quotient, binary_remainder, remainder

# Example usage for Restoring Division with 8-bit binary input:
dividend = '10001001'  # 8-bit Binary representation of 137
divisor = '00000101'   # 8-bit Binary representation of 5
binary_quotient, decimal_quotient, binary_remainder, decimal_remainder = restoring_division(dividend, divisor)
print("Restoring Division:")
print(f"Binary Quotient: {binary_quotient}, Decimal Quotient: {decimal_quotient}")
print(f"Binary Remainder: {binary_remainder}, Decimal Remainder: {decimal_remainder}")

# Example usage for Non-Restoring Division with 8-bit binary input:
dividend = '10001001'  # 8-bit Binary representation of 137
divisor = '00000101'   # 8-bit Binary representation of 5
binary_quotient, decimal_quotient, binary_remainder, decimal_remainder = non_restoring_division(dividend, divisor)
print("Non-Restoring Division:")
print(f"Binary Quotient: {binary_quotient}, Decimal Quotient: {decimal_quotient}")
print(f"Binary Remainder: {binary_remainder}, Decimal Remainder: {decimal_remainder}")

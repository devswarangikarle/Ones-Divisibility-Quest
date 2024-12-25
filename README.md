# Ones-Divisibility-Quest

In a quiet town, Neha stumbled upon a curious puzzle. Her friend, Rohan, gave her a positive integer k and asked her to find the length of the smallest positive number n that is divisible by k. The catch? The number n can only contain the digit 1. If such a number exists, Neha needs to figure out its length, but if it’s impossible, she should return -1. Can you help Neha solve this tricky puzzle?

def smallest_ones_divisible_by_k(k):
    # Remainder tracking set
    remainder = 0
    visited = set()
    
    for length in range(1, k + 1):
        # Update the remainder
        remainder = (remainder * 10 + 1) % k
        if remainder == 0:
            return length  # Found the length of the number
        if remainder in visited:
            return -1  # Cycle detected
        visited.add(remainder)
    
    return -1  # If no solution is found

# Input
k = int(input().strip())
print(smallest_ones_divisible_by_k(k))

# ============================================================
# ACTIVITY 1 (Set 1)
# Accept 10 integer elements for an array and print the sum.
# ============================================================
print("\nACTIVITY 1")
arr = []
for i in range(10):
    arr.append(int(input(f"Enter element {i+1}: ")))
print("Sum of elements:", sum(arr))


# ============================================================
# ACTIVITY 2 (Set 1)
# Accept 20 integers and print maximum 3 and minimum 3
# without sorting.
# ============================================================
print("\nACTIVITY 2")
arr = []
for i in range(20):
    arr.append(int(input(f"Enter element {i+1}: ")))

mins = [float('inf')] * 3
maxs = [float('-inf')] * 3

for num in arr:
    # for minimums
    if num < mins[0]:
        mins = [num, mins[0], mins[1]]
    elif num < mins[1]:
        mins = [mins[0], num, mins[1]]
    elif num < mins[2]:
        mins[2] = num

    # for maximums
    if num > maxs[0]:
        maxs = [num, maxs[0], maxs[1]]
    elif num > maxs[1]:
        maxs = [maxs[0], num, maxs[1]]
    elif num > maxs[2]:
        maxs[2] = num

print("Minimum 3 elements:", mins)
print("Maximum 3 elements:", maxs)


# ============================================================
# ACTIVITY 3 (Set 1)
# Reverse 10 array elements.
# ============================================================
print("\nACTIVITY 3")
arr = []
for i in range(10):
    arr.append(int(input(f"Enter element {i+1}: ")))

print("Reversed array:", arr[::-1])


# ============================================================
# ACTIVITY 4 (Set 1)
# Count how many students scored each mark (0-100).
# ============================================================
print("\nACTIVITY 4")
N = 30
marks = []
for i in range(N):
    marks.append(int(input(f"Enter mark of student {i+1}: ")))

count = [0] * 101
for m in marks:
    if 0 <= m <= 100:
        count[m] += 1

for i in range(101):
    if count[i] > 0:
        print(f"Students scoring {i}: {count[i]}")


# ============================================================
# ACTIVITY 5 (Set 1)
# Count students in percentage ranges.
# ============================================================
print("\nACTIVITY 5")
range_count = [0] * 10

for m in marks:
    if 0 <= m <= 100:
        index = min(m // 10, 9)
        range_count[index] += 1

for i in range(10):
    print(f"{i*10} to {i*10+10}% :", range_count[i])


# ============================================================
# ACTIVITY 6 (Set 1)
# Count number of digits.
# ============================================================
print("\nACTIVITY 6")
num = int(input("Enter a number: "))
print("Number of digits:", len(str(abs(num))))


# ============================================================
# ACTIVITY 7 (Set 1)
# Count frequency again (same as activity 4).
# ============================================================
print("\nACTIVITY 7")
count = [0] * 101
for m in marks:
    if 0 <= m <= 100:
        count[m] += 1

for i in range(101):
    if count[i] > 0:
        print(f"Students scoring {i}: {count[i]}")


# ============================================================
# ACTIVITY 8 (Set 1)
# Decimal to binary.
# ============================================================
print("\nACTIVITY 8")
dec = int(input("Enter decimal number: "))
print("Binary representation:", bin(dec)[2:])


# ============================================================
# ACTIVITY 9 (Set 1)
# Binary to decimal.
# ============================================================
print("\nACTIVITY 9")
binary = input("Enter binary number: ")
print("Decimal equivalent:", int(binary, 2))


# ============================================================
# ACTIVITY 10 (Set 1)
# Smallest exact divisor other than 1.
# ============================================================
print("\nACTIVITY 10")
num = int(input("Enter a number: "))
divisor = None
for i in range(2, num + 1):
    if num % i == 0:
        divisor = i
        break
print("Smallest divisor other than 1:", divisor)


# ============================================================
# ACTIVITY 6 (Set 2)
# Factorial of a number.
# ============================================================
print("\nACTIVITY 6 (FACTORIAL)")
n = int(input("Enter N: "))
fact = 1
for i in range(1, n + 1):
    fact *= i
print("Factorial:", fact)


# ============================================================
# ACTIVITY 7 (Set 2)
# Average of 10 integers.
# ============================================================
print("\nACTIVITY 7 (AVERAGE)")
arr = []
for i in range(10):
    arr.append(int(input(f"Enter value {i+1}: ")))
print("Average:", sum(arr) / 10)


# ============================================================
# ACTIVITY 8 (Set 2)
# Train crosses pole -> find length.
# ============================================================
print("\nACTIVITY 8 (TRAIN LENGTH)")
x = float(input("Enter speed (km/hr): "))
y = float(input("Enter time (seconds): "))
speed_mps = x * 1000 / 3600
length = speed_mps * y
print("Length of train (m):", length)


# ============================================================
# ACTIVITY 9 (Set 2)
# Train passes man -> find speed.
# ============================================================
print("\nACTIVITY 9 (TRAIN SPEED)")
X = float(input("Enter train length (m): "))
Y = float(input("Enter time (seconds): "))
man_speed = 5 * 1000 / 3600
train_speed_mps = (X / Y) + man_speed
print("Speed of train (km/hr):", train_speed_mps * 3600 / 1000)


# ============================================================
# ACTIVITY 10 (Set 2)
# Two trains opposite -> time to pass driver.
# ============================================================
print("\nACTIVITY 10 (TWO TRAINS)")
X = float(input("Enter speed of train X (km/hr): "))
Y = float(input("Enter speed of train Y (km/hr): "))

faster = max(X, Y)
slower = min(X, Y)

relative_speed = (faster + slower) * 1000 / 3600
time = 500 / relative_speed

print("Time taken (seconds):", time)

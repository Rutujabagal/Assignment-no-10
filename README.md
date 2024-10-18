Tu = float(input("Enter the value of ultimate tensile strength (Tu): "))

fy = float(input("Enter the value of yield strength of steel (fy): "))

fu = float(input("Enter the value of ultimate strength of steel (fu): "))

fub = float(input("Enter the value of ultimate strength of bolt (fub): "))

Gamma_mo = float(input("Enter the value of partial factor of safety Gamma_mo: "))

Gamma_m1 = float(input("Enter the value of partial factor of safety Gamma_m1: "))

Gamma_mb = float(input("Enter the value of partial factor of safety Gamma_mb: "))

# Gross Area Calculation

print("Gross Area Required")

Agreq = (1.1 * Tu * 1000) / fy

print("The value of gross area required is:", Agreq)

# Selection of section

Ag = float(input("Enter the value of gross area of steel (Ag): "))

t = float(input("Enter the value of least thickness (t): "))

# Design of connections

d = float(input("Enter the value of diameter of bolt (d): "))

do = d + 2

print("The diameter of bolt hole is:", do)

# Minimum pitch distance as per IS code

pmin = 2.5 * d

print("The minimum pitch distance is:", pmin)

# Edge distance as per IS 800

e = 1.5 * d

print("The edge distance is:", e)

# Bolt strength calculations

nn = float(input("Number of shear planes with threads intercepting the shear plane (nn): "))

ns = float(input("Number of shear planes without threads (ns): "))

Anb = 0.78 * (0.7854 * d * d)

print("Threaded area of bolt is:", Anb)

Asb = 0.7854 * d * d

print("Plane shank area of bolt is:", Asb)

Vdsb = (fub / (1.732 * Gamma_mb)) * (nn * Anb + ns * Asb) * 10**-3

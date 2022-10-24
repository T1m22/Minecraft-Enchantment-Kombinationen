# Zahlenformatierung
def value(number):
    return ("{:,}".format(number))

# Berechnung der Fakultät
def factorial(a):
    fac = 1
    for i in range(1, a + 1):
        fac = fac * i
    return fac

# Auflistung der Item Enchantments
def enchants(x):
    if x == "Schaufel" or x == "Hacke" or x == "Spitzhacke":
        enchants = [5, 4, 3, 1, 1]
    if x == "Axt":
        enchants = [5, 4, 15, 3, 1, 1]
    if x == "Schwert":
        enchants = [15, 3, 3, 3, 2, 2, 1, 1]
    if x == "Helm" or x == "Schildkrötenpanzer":
        enchants = [16, 3, 3, 3, 1, 1, 1, 1]
    if x == "Brustplatte":
        enchants = [16, 3, 3, 1, 1, 1]
    if x == "Hose":
        enchants = [16, 3, 3, 3, 1, 1, 1]
    if x == "Stiefel":
        enchants = [16, 5, 4, 3, 3, 3, 1, 1, 1]
    if x == "Bogen":
        enchants = [2, 5, 3, 2, 1, 1]
    if x == "Armbrust":
        enchants = [5, 3, 3, 1, 1]
    if x == "Dreizack":
        enchants = [3, 3, 1, 5, 3, 1, 1]
    if x == "Angel":
        enchants = [3, 3, 3, 1, 1]
    if x == "Schere":
        enchants = [5, 3, 1, 1]
    if x == "Schild" or x == "Elytra" or x == "Feuerzeug" or x == "Karottenrute" or x == "Wirrpilzrute":
        enchants = [3, 1, 1]
    if x == "Kompass":
        enchants = [1]
    return enchants

# Möglichkeiten für 1 Enchantment
def enchantments1():
    enchantments = enchants(item)
    total = factorial(1) * sum(enchantments)
    return total

# Möglichkeiten für 2 Enchantments
def enchantments2():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken = 0
    for level1 in range(len(enchantments) - 1):
        taken += enchantments[level1]
        levels_total = sum(enchantments) - taken
        # Beim Dreizack schließt sich Enchantment 1 (Riptide) mit Enchantment 2 (Loyalty) und 3 (Channeling) aus
        if item == "Dreizack" and level1 == 0:
            levels_total = sum(enchantments) - (taken + enchantments[level1 + 1] + enchantments[level1 + 2])
        E += enchantments[level1] * levels_total
    total = factorial(2) * E
    return total  

# Möglichkeiten für 3 Enchantments
def enchantments3():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    sub_levels2 = 0
    for level1 in range(len(enchantments) - 2):
        taken_level1 += enchantments[level1]
        # Beim Dreizack schließt sich Enchantment 1 (Riptide) mit Enchantment 2 (Loyalty) und 3 (Channeling) aus
        if item == "Dreizack" and level1 == 0:
            for level2 in range(level1 + 3, len(enchantments) - 1):
                taken_level2 += enchantments[level2]
                levels_total = levels_total - (taken_level1 + taken_level2 + enchantments[level1 + 1] + enchantments[level1 + 2])
                sub_levels2 = enchantments[level2] * levels_total
                E += enchantments[level1] * sub_levels2
                levels_total = sum(enchantments)
            taken_level2 = 0
        else:
            for level2 in range(level1 + 1, len(enchantments) - 1):
                taken_level2 += enchantments[level2]
                levels_total = levels_total - (taken_level1 + taken_level2)
                sub_levels2 = enchantments[level2] * levels_total
                E += enchantments[level1] * sub_levels2
                levels_total = sum(enchantments)
            taken_level2 = 0
    total = factorial(3) * E
    return total

# Möglichkeiten für 4 Enchantments       
def enchantments4():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    sub_levels3 = 0
    for level1 in range(len(enchantments) - 3):
        taken_level1 += enchantments[level1]
        # Beim Dreizack schließt sich Enchantment 1 (Riptide) mit Enchantment 2 (Loyalty) und 3 (Channeling) aus
        if item == "Dreizack" and level1 == 0:
            for level2 in range(level1 + 3, len(enchantments) - 2):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 1):
                    taken_level3 += enchantments[level3]
                    levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + enchantments[level1 + 1] \
                    + enchantments[level1 + 2])
                    sub_levels3 = enchantments[level2] * enchantments[level3] * levels_total
                    E += enchantments[level1] * sub_levels3
                    levels_total = sum(enchantments)
                taken_level3 = 0
            taken_level2 = 0
        else:
            for level2 in range(level1 + 1, len(enchantments) - 2):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 1):
                    taken_level3 += enchantments[level3]
                    levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3)
                    sub_levels3 = enchantments[level2] * enchantments[level3] * levels_total
                    E += enchantments[level1] * sub_levels3
                    levels_total = sum(enchantments)
                taken_level3 = 0
            taken_level2 = 0
    total = factorial(4) * E
    return total

# Möglichkeiten für 5 Enchantments
def enchantments5():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    taken_level4 = 0
    sub_levels4 = 0
    for level1 in range(len(enchantments) - 4):
        taken_level1 += enchantments[level1]
        # Beim Dreizack schließt sich Enchantment 1 (Riptide) mit Enchantment 2 (Loyalty) und 3 (Channeling) aus
        if item == "Dreizack" and level1 == 0:
            for level2 in range(level1 + 3, len(enchantments) - 3):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 2):
                    taken_level3 += enchantments[level3]
                    for level4 in range(level3 + 1, len(enchantments) - 1):
                        taken_level4 += enchantments[level4]
                        levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + enchantments[level1 + 1] \
                        + enchantments[level1 + 2])
                        sub_levels4 = enchantments[level2] * enchantments[level3] * enchantments[level4] * levels_total
                        E += enchantments[level1] * sub_levels4
                        levels_total = sum(enchantments)
                    taken_level4 = 0
                taken_level3 = 0
            taken_level2 = 0
        else:
            for level2 in range(level1 + 1, len(enchantments) - 3):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 2):
                    taken_level3 += enchantments[level3]
                    for level4 in range(level3 + 1, len(enchantments) - 1):
                        taken_level4 += enchantments[level4]
                        levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4)
                        sub_levels4 = enchantments[level2] * enchantments[level3] * enchantments[level4] * levels_total
                        E += enchantments[level1] * sub_levels4
                        levels_total = sum(enchantments)
                    taken_level4 = 0
                taken_level3 = 0
            taken_level2 = 0
    total = factorial(5) * E
    return total

# Möglichkeiten für 6 Enchantments
def enchantments6():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    taken_level4 = 0
    taken_level5 = 0
    sub_levels5 = 0
    for level1 in range(len(enchantments) - 5):
        taken_level1 += enchantments[level1]
        # Beim Dreizack schließt sich Enchantment 1 (Riptide) mit Enchantment 2 (Loyalty) und 3 (Channeling) aus
        if item == "Dreizack" and level1 == 0:
            for level2 in range(level1 + 3, len(enchantments) - 4):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 3):
                    taken_level3 += enchantments[level3]
                    for level4 in range(level3 + 1, len(enchantments) - 2):
                        taken_level4 += enchantments[level4]
                        for level5 in range(level4 + 1, len(enchantments) - 1):
                            taken_level5 += enchantments[level5]
                            levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + taken_level5 \
                            + enchantments[level1 + 1] + enchantments[level1 + 2])
                            sub_levels5 = enchantments[level2] * enchantments[level3] * enchantments[level4] * enchantments[level5] \
                            * levels_total
                            E += enchantments[level1] * sub_levels5
                            levels_total = sum(enchantments)
                        taken_level5 = 0
                    taken_level4 = 0
                taken_level3 = 0
            taken_level2 = 0
        else:
            for level2 in range(level1 + 1, len(enchantments) - 4):
                taken_level2 += enchantments[level2]
                for level3 in range(level2 + 1, len(enchantments) - 3):
                    taken_level3 += enchantments[level3]
                    for level4 in range(level3 + 1, len(enchantments) - 2):
                        taken_level4 += enchantments[level4]
                        for level5 in range(level4 + 1, len(enchantments) - 1):
                            taken_level5 += enchantments[level5]
                            levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + taken_level5)
                            sub_levels5 = enchantments[level2] * enchantments[level3] * enchantments[level4] * enchantments[level5] \
                            * levels_total
                            E += enchantments[level1] * sub_levels5
                            levels_total = sum(enchantments)
                        taken_level5 = 0
                    taken_level4 = 0
                taken_level3 = 0
            taken_level2 = 0
    total = factorial(6) * E
    return total 

# Möglichkeiten für 7 Enchantments
def enchantments7():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    taken_level4 = 0
    taken_level5 = 0
    taken_level6 = 0
    sub_levels6 = 0
    for level1 in range(len(enchantments) - 6):
        taken_level1 += enchantments[level1]
        for level2 in range(level1 + 1, len(enchantments) - 5):
            taken_level2 += enchantments[level2]
            for level3 in range(level2 + 1, len(enchantments) - 4):
                taken_level3 += enchantments[level3]
                for level4 in range(level3 + 1, len(enchantments) - 3):
                    taken_level4 += enchantments[level4]
                    for level5 in range(level4 + 1, len(enchantments) - 2):
                        taken_level5 += enchantments[level5]
                        for level6 in range(level5 + 1, len(enchantments) - 1):
                            taken_level6 += enchantments[level6]
                            levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + taken_level5 \
                            + taken_level6)
                            sub_levels6 = enchantments[level2] * enchantments[level3] * enchantments[level4] * enchantments[level5] \
                            * enchantments[level6] * levels_total
                            E += enchantments[level1] * sub_levels6
                            levels_total = sum(enchantments)
                        taken_level6 = 0
                    taken_level5 = 0
                taken_level4 = 0
            taken_level3 = 0
        taken_level2 = 0
    total = factorial(7) * E
    return total

# Möglichkeiten für 8 Enchantments
def enchantments8():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    taken_level4 = 0
    taken_level5 = 0
    taken_level6 = 0
    taken_level7 = 0
    sub_levels7 = 0
    for level1 in range(len(enchantments) - 7):
        taken_level1 += enchantments[level1]
        for level2 in range(level1 + 1, len(enchantments) - 6):
            taken_level2 += enchantments[level2]
            for level3 in range(level2 + 1, len(enchantments) - 5):
                taken_level3 += enchantments[level3]
                for level4 in range(level3 + 1, len(enchantments) - 4):
                    taken_level4 += enchantments[level4]
                    for level5 in range(level4 + 1, len(enchantments) - 3):
                        taken_level5 += enchantments[level5]
                        for level6 in range(level5 + 1, len(enchantments) - 2):
                            taken_level6 += enchantments[level6]
                            for level7 in range(level6 + 1, len(enchantments) - 1):
                                taken_level7 += enchantments[level7]
                                levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + taken_level5 \
                                + taken_level6 + taken_level7)
                                sub_levels7 = enchantments[level2] * enchantments[level3] * enchantments[level4] * enchantments[level5] \
                                * enchantments[level6] * enchantments[level7] * levels_total
                                E += enchantments[level1] * sub_levels7
                                levels_total = sum(enchantments)
                            taken_level7 = 0
                        taken_level6 = 0
                    taken_level5 = 0
                taken_level4 = 0
            taken_level3 = 0
        taken_level2 = 0
    total = factorial(8) * E
    return total 

# Möglichkeiten für 9 Enchantments
def enchantments9():
    enchantments = enchants(item)
    levels_total = sum(enchantments)
    E = 0
    taken_level1 = 0
    taken_level2 = 0
    taken_level3 = 0
    taken_level4 = 0
    taken_level5 = 0
    taken_level6 = 0
    taken_level7 = 0
    taken_level8 = 0
    sub_levels8 = 0
    for level1 in range(len(enchantments) - 8):
        taken_level1 += enchantments[level1]
        for level2 in range(level1 + 1, len(enchantments) - 7):
            taken_level2 += enchantments[level2]
            for level3 in range(level2 + 1, len(enchantments) - 6):
                taken_level3 += enchantments[level3]
                for level4 in range(level3 + 1, len(enchantments) - 5):
                    taken_level4 += enchantments[level4]
                    for level5 in range(level4 + 1, len(enchantments) - 4):
                        taken_level5 += enchantments[level5]
                        for level6 in range(level5 + 1, len(enchantments) - 3):
                            taken_level6 += enchantments[level6]
                            for level7 in range(level6 + 1, len(enchantments) - 2):
                                taken_level7 += enchantments[level7]
                                for level8 in range(level7 + 1, len(enchantments) - 1):
                                    taken_level8 += enchantments[level8]
                                    levels_total = levels_total - (taken_level1 + taken_level2 + taken_level3 + taken_level4 + taken_level5 \
                                    + taken_level6 + taken_level7 + taken_level8)
                                    sub_levels8 = enchantments[level2] * enchantments[level3] * enchantments[level4] * enchantments[level5] \
                                    * enchantments[level6] * enchantments[level7] * enchantments[level8] * levels_total
                                    E += enchantments[level1] * sub_levels8
                                    levels_total = sum(enchantments)
                                taken_level8 = 0
                            taken_level7 = 0
                        taken_level6 = 0
                    taken_level5 = 0
                taken_level4 = 0
            taken_level3 = 0
        taken_level2 = 0
    total = factorial(9) * E
    return total     

item = input("\nItem: ")

def total_enchantments():
    total = 0
    enchantments = enchants(item)
    for n in range(1, len(enchantments) + 1):
        if n == 1:
            print(f"\nE{n} = {value(enchantments1())}")
            total += enchantments1()
        if n == 2:
            print(f"E{n} = {value(enchantments2())}")
            total += enchantments2()
        if n == 3:
            print(f"E{n} = {value(enchantments3())}")
            total += enchantments3()
        if n == 4:
            print(f"E{n} = {value(enchantments4())}")
            total += enchantments4()
        if n == 5:
            print(f"E{n} = {value(enchantments5())}")
            total += enchantments5()
        if n == 6:
            print(f"E{n} = {value(enchantments6())}")
            total += enchantments6()
        if n == 7:
            # Der Dreizack kann nur höchstens 6 Enchantments haben, weil sich Riptide mit Loyalty und Channeling ausschließt
            if item == "Dreizack":
                total += 0
            else: 
                print(f"E{n} = {value(enchantments7())}")
                total += enchantments7()
        if n == 8:
            print(f"E{n} = {value(enchantments8())}")
            total += enchantments8()
        if n == 9:
            print(f"E{n} = {value(enchantments9())}")
            total += enchantments9()
    print(f"\nGesamtanzahl der möglichen Enchantments: {value(total)}\n")

total_enchantments()

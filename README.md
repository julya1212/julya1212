
combinations = []

for i in range(1, 10):
    for j in range(1, 10):
        for k in range(1, 10):
            for l in range(1, 10):
                s = {i,j,k,l}
                if len(s)==4:
                    combinations.append(str(i)+str(j)+str(k)+str(l))

four_numbers = "
attempt = 1
result = False

print('Please think of a number with 4 different digits 1..9.')

while not result:

    attempt += 1

    if attempt > len(combinations):
        attempt = 0

     whilecombinations[attempt] == '0000':
        attempt += 1

        if attempt > len(combinations):
            attempt = 0

    print(combinations[attempt])
    print(
        f'My guess is: {combinations[attempt]}. Enter the number of bulls and cows.')
    oxes, cows = [int(i) for i in input().split()]

    current_number = combinations[attempt]
    first, second, third, fourth = [i for i in current_number]

    if cows == 0 and oxes == 0:
        for i in range(combinations.__len__()):
            if combinations[i] != "0000":
                cur_cheching = combinations[i]
                amount = 0

                for k in range(4):
                    if cur_cheching[k] == first or cur_cheching[k] == second or\
                            cur_cheching[k] == third or cur_cheching[k] == fourth:
                        amount += 1
                if amount > 0:
                    combinations[i] = "0000"

    if cows == 0 and oxes == 4:
        result = True
        break

    if cows == 0:
        for i in range(combinations.__len__()):
            if combinations[i] != "0000":
                cur_cheching = combinations[i]
                amount = 0

                if cur_cheching[0] == first:
                    amount += 1
                if cur_cheching[1] == second:
                    amount += 1
                if cur_cheching[2] == third:
                    amount += 1
                if cur_cheching[3] == fourth:
                    amount += 1

                if amount != oxes:
                    combinations[i] = "0000"

    elif cows == 1 and oxes == 0:
        for i in range(combinations.__len__()):
            if combinations[i] != "0000":
                cur_cheching = combinations[i]
                amount = 0

                if cur_cheching[0] == first:
                    amount += 1
                if cur_cheching[1] == second:
                    amount += 1
                if cur_cheching[2] == third:
                    amount += 1
                if cur_cheching[3] == fourth:
                    amount += 1

                amount_1 = 0

                for k in range(4):
                    if cur_cheching[k] == first or cur_cheching[k] == second or cur_cheching[k] == third or cur_cheching[k] == fourth:
                        amount_1 += 1

                if amount != 0:
                    combinations[i] = "0000"
                if amount_1 != 1:
                    combinations[i] = "0000"
    else:
        for i in range(combinations.__len__()):
            if combinations[i] != "0000":
                cur_cheching = combinations[i]
                amount = 0

                if cur_cheching[0] == first:
                    amount += 1
                if cur_cheching[1] == second:
                    amount += 1
                if cur_cheching[2] == third:
                    amount += 1
                if cur_cheching[3] == fourth:
                    amount += 1

                amount_1 = 0

                for k in range(4):
                    if cur_cheching[k] == first or cur_cheching[k] == second or cur_cheching[k] == third or cur_cheching[k] == fourth:
                        amount_1 += 1

                if amount != oxes or (amount_1-amount) != cows:
                    combinations[i] = "0000"

print(f'Your number is {combinations[attempt]}. It took 4 trials.')

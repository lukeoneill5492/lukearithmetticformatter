# lukearithmetticformatter
def arithmetic_arranger(problems, ans = False):
    for problem in problems:
        split_problem = problem.split()
        first_num_is = split_problem[0]
        try:
            first_num = int(first_num_is)
        except:
            print("Error: Numbers must only contain digits.")
            quit()
        operator = split_problem[1]
        second_num_is = split_problem[2]
        try:
            second_num = int(second_num_is)
        except:
            print("Error: Numbers must only contain digits.")
            quit()
        if len(problems) > 5:
            print('Error: Too many problems.')
            quit()
        elif operator not in ["+", "-"]:
            print("Error: Operator must be '+' or '-'.")
            quit()
        elif len(str(first_num)) > 4 or len(str(second_num)) > 4:
            print("Error: Numbers cannot be more than four digits.")
            quit()
        else:
            width = max(len(str(first_num)), len(str(second_num)))
            #print(width)
            first_line = ""
            second_line = ""
            third_line = ""
            fourth_line = ""
            #print(problem)

            if operator == "+":
                answers = first_num + second_num
            elif operator == "-":
                answers = first_num - second_num
            else:
                print("Error: Operator must be '+' or '-'.")

            first_line += str(first_num).rjust(width + 6)
            second_line += str(operator).rjust(5) + " " + str(second_num).rjust(width)
            third_line += "    " + "-" * (width+2)
            fourth_line += str(answers).rjust(width + 6)
            #print(first_line + '\n' + second_line + '\n' + third_line + '\n' + fourth_line)

        if ans == True:
            print(first_line + '\n' + second_line + '\n' + third_line + '\n' + fourth_line)
            quit()
        if ans == False:
            print(first_line + '\n' + second_line + '\n' + third_line)
            quit()

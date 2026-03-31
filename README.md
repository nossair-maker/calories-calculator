# calories-calculator
#python algorithm that calculate the calories you should eat to reach a certain weight
#an algorithm that count how many calories must be gained to achieve a certain physic:

#variables:

w=int(input("give your weight: "))
h=int(input("give your height: "))
Age=int(input("give your age: "))
G=int(input("give your goal weight: "))
tr=float(input("how many times you train per week : "))
if tr > 7:
    print("incorrect input")
elif tr > 6:
    A =int(1.725)
elif tr > 3:
    A =int(1.55)
elif tr > 1:
    A = (1.375)
else:
    print("sorry, can't help you.")

while tr>0 and w>0 and w!=0 and h>0 and Age>6 and G>0 and G!=0:
#conditions:
# A is the activity level:
    D = int(input("give the number of days to achieve  that goal : "))
    gender = str(input("give your gender: "))

    #result may change based on the gender too:

    if gender=="male":
    # calculation:
        calories=((10*w)+6.25*h-5*Age+5)*A+(G-w)*7700/D
        protein = (calories * 0.3) // 4
        carbs = (calories * 0.3) // 4
        fats = (calories * 0.3) //4
        total = protein + carbs + fats
    elif gender=="female":
    #calculation:
        calories=((10*w)+6.25*h-5*Age-161)*A+(G-w)*7700/D
        protein=(calories*0.3)//4
        carbs=(calories*0.3)//4
        fats=(calories*0.3)//4
        total=protein+carbs+fats
#final result:
    print(f"your goal for daily calories should be:",calories,"kcal,which mean that you "
    ,carbs,"g of carbs, "
    ,fats,"g of fats"
    ,protein,"g of protein "
    "so totaly:",total,"g")
    break
else:
    print("sorry, wrong input,check if all the information are correct. ")
#finally the algorithm should give the result if the user insert all the information correctly:

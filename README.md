# calories-calculator
# A Python algorithm that calculates the calories you should eat to reach a certain weight
# The algorithm counts how many calories must be gained/lost to achieve a certain physique

# ─────────────────────────────────────────────
# Variables / User Input
# ─────────────────────────────────────────────

    w   = int(input("Enter your current weight (kg): "))
    h   = int(input("Enter your height (cm): "))
    Age = int(input("Enter your age: "))
    G   = int(input("Enter your goal weight (kg): "))
    tr  = float(input("How many times do you train per week? "))

    # ─────────────────────────────────────────────
    # Activity Level (A) — based on training frequency
    # ─────────────────────────────────────────────

    if tr > 7:
        print("Incorrect input: training days cannot exceed 7.")
    elif tr > 6:
        A = 1.725   # Very active
    elif tr > 3:
        A = 1.55    # Moderately active
    elif tr > 1:
        A = 1.375   # Lightly active
    else:
        print("Sorry, can't help you with that training frequency.")

    # ─────────────────────────────────────────────
    # Main Calculation
    # ─────────────────────────────────────────────

    while tr > 0 and w > 0 and h > 0 and Age > 6 and G > 0:

        D      = int(input("Enter the number of days to achieve your goal: "))
        gender = str(input("Enter your gender (male/female): ")).strip().lower()

        if gender == "male":
            # Mifflin-St Jeor Equation for males
            calories = ((10 * w) + (6.25 * h) - (5 * Age) + 5) * A + (G - w) * 7700 / D
            protein  = (calories * 0.3) // 4
            carbs    = (calories * 0.3) // 4
            fats     = (calories * 0.3) // 4
            total    = protein + carbs + fats

        elif gender == "female":
            # Mifflin-St Jeor Equation for females
            calories = ((10 * w) + (6.25 * h) - (5 * Age) - 161) * A + (G - w) * 7700 / D
            protein  = (calories * 0.3) // 4
            carbs    = (calories * 0.3) // 4
            fats     = (calories * 0.3) // 4
            total    = protein + carbs + fats

        #  ─────────────────────────────────────────────
        # Final Result
        # ─────────────────────────────────────────────

        print(
            f"\n✅ Your daily calorie goal: {calories:.1f} kcal\n"
            f"   🥩 Protein : {protein:.0f} g\n"
            f"   🍞 Carbs   : {carbs:.0f} g\n"
            f"   🥑 Fats    : {fats:.0f} g\n"
            f"   📦 Total macros: {total:.0f} g"
        )
        break

    else:
        print("Sorry, wrong input. Please check that all values are correct.")

    # Note: The algorithm returns results only when all inputs are valid.

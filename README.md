def main():
    print("Welcome to the Car Driving Interface Simulator!")
    print("Choose a car:")
    for idx, car in enumerate(cars):
        print(f"{idx + 1}. {car}")

    choice = int(input("Enter the number of your choice: ")) - 1
    selected_car = cars[choice]
    print(f"You selected: {selected_car}")

    total_points = 0

    while True:
        print("\nAvailable rewards:")
        for idx, reward in enumerate(rewards):
            print(f"{idx + 1}. {reward}")

        action = input("Enter the number of the reward you want to collect (Press 'q' to quit): ")

        if action.lower() == "q":
            break

        try:
            reward_choice = int(action) - 1
            selected_reward = rewards[reward_choice]
            total_points += selected_reward.points
            print(f"Collected: {selected_reward}")
        except (ValueError, IndexError):
            print("Invalid choice. Please try again.")

    print(f"\nTotal points collected: {total_points}")
    print("Thank you for using the Car Driving Interface Simulator!")

if __name__ == "__main__":
    main()

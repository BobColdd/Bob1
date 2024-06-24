import time  # Import the time module for sleep and current time functions

def main():
    while True:  # Infinite loop to continuously update and display the time
        current_time = time.localtime()  # Get the current time in local timezone
        
        # Extract hour, minute, and second from current_time
        hour = current_time.tm_hour
        minute = current_time.tm_min
        second = current_time.tm_sec
        
        # Adjust for EAT (UTC+3) timezone
        hour += 3
        if hour >= 24:  # Wrap around if hour goes beyond 24
            hour -= 24
        
        # Format the time components into a string for display
        time_str = f"{hour:02}:{minute:02}:{second:02}"
        
        # Clear the screen for a cleaner display (works in some environments)
        print("\033[H\033[J")
        
        # Display the current time
        print(f"Current EAT Time: {time_str}")
        
        # Wait for 1 second before updating the time again
        time.sleep(1)

if __name__ == "__main__":
    main()

# song-time-adder
On days when I forget to start my stopwatch or don't want that kinda pressure when I'm running, I add up the length of the songs I listened to afterwards.
def main():
    time = "h"
    total_min = 0
    total_sec = 0
    while time.lower() != "q":
        time = input("Please enter the length of the song or press q to quit.\n> ")
        if time.lower() == "q":
            print("Total time: %s minutes and %s seconds." % (total_min, total_sec))
            break
        time_list = time.split(":")
        if len(time_list) != 2:
            print("Invalid input. Enter time in format 00:00")
            continue
        total_min += int(time_list[0])
        total_sec += int(time_list[1])
        n = total_sec // 60
        if total_sec >= 60:
            total_sec -= (60 * n)
            total_min += n
        print("Your total time is %s minutes and %s seconds." % (total_min, total_sec))

main()

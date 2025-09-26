from gpiozero import Button, LED from signal import pause

touch_sensor = Button(17) led = LED(27)

print("Program running. Touch the sensor to toggle the LED.") print("Press Ctrl+C in the console or the stop button in Thonny to exit.")

def toggle_led(): if led.is_lit: led.off() print("LED OFF") else: led.on() print("LED ON")

touch_sensor.when_pressed = toggle_led

try: pause()

except KeyboardInterrupt: # This block will run if you press Ctrl+C in the console. print("\nExiting program.")

finally: print("Cleaning up GPIO...") # When it's interrupted, the script ends, and the objects # are garbage collected, freeing the pins. print("Done.")

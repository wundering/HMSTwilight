# HMS Twilight SmartThings SmartApp
My attempt at a whole house SmartApp.

One thing to note:
- I don't use runIn/unschedule for monitoring.  Contrary to what I read about runIn, I never had any trouble with runIn once I figured out that it can't be a private function that is passed into it since the runIn process is executed in the server's context, not mine.  The biggest reason I chose to use runEvery5Minutes and check for conditions that warranted actions, is that unschedule requires a call to the servers - and if the current connection is slow then my actions may be delayed by that call to the server.  At least as far as I could tell it wasn't asynchronous.

What does it do so far:
- When you walk into the master bedroom during the day all the lights come on.
- When you walk into the master bathroom at night the 'potty' room lights come on at 20%.
- If you switch off the master bedroom light, all lights go on.
- The '1' switch on my MiniMote toggles the Home and Do Not Disturb modes.
- If either door to the laundry room opens the light turns on.
- On a five minute timer it checks to see if the master bedroom lights or the laundry room light should be turned off.
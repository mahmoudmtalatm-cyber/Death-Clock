# Death Clock

A single-page web replica of the Death Clock from Vsauce and The Curiosity Box, built with plain HTML, CSS and JavaScript. No build step, no dependencies, no server.

Answer a short survey, press the red button, and a seven-segment display counts down the seconds you have left. The grey button switches the display to a normal clock.

> *Omnes vulnerant, ultima necat.*

## Features

- Physical-clock look: faux-wood case, red seven-segment LED display, metal knobs and buttons
- One-time survey of 13 questions that sets your seconds
- Red button starts the countdown, grey button switches between countdown and clock
- Brightness knob on the left, alarm buttons and adjust knob on the right
- Works offline once saved; only the Google Fonts stylesheet needs a connection, with system fonts as fallback
- Responsive down to phone width

## Not resettable

Once **Lock it in** is pressed at the end of the survey, the seconds are fixed. The page has no reset button and no way to retake the survey. The end time is saved in the browser, so the countdown keeps running while the page is closed. At zero the display stops and blinks.

This is a limit of plain web pages, not a guarantee. Clearing the site's browser data or editing `localStorage` in developer tools starts over.

## Run

Open `death-clock.html` in any modern browser, or host the file on any static host such as GitHub Pages.

## Usage

1. Answer the survey. Answers are saved as you go.
2. Press **Lock it in**. The display shows your seconds.
3. Press the **red button** to begin the countdown.
4. Press the **grey button** to switch between the countdown and the clock.

### Alarm

- **Alarm** button: turns the alarm on or off
- **Set** button: press once for the hour, again for the minutes, a third time to finish
- **Adjust** knob: drag it in a circle, scroll over it, or use the arrow keys
- Any button silences a ringing alarm

### Brightness

Drag, scroll or use the arrow keys on the left knob. Five levels.

## How the estimate works

The estimate is a simple model written for this project, not actuarial data. It starts from a baseline life expectancy by sex, then adds or subtracts years for body mass index, smoking, alcohol, exercise, diet, sleep, stress, family history, long-term conditions and region. The remaining years are converted to seconds using the mean Gregorian year of 31,556,952 seconds, so 40 years is 1,262,278,080 seconds. A soft floor keeps the result positive for older users.

The result is meant for reflection and is not a medical prediction.

## About the original

The Death Clock is sold by The Curiosity Box and Inq Factory. It uses a true seven-segment display with mechanical controls, runs offline, and keeps the countdown on a backup battery. It was introduced in the Vsauce video "All The Ghosts You Will Be", part of the Mox Nox project.

The original survey questions are not public. The questions here cover the topics that have been described: age, weight, habits and more.

## Customising

Everything lives in `death-clock.html`.

- **Survey questions:** the `Q` array in the script
- **Estimate weights:** the `estimate` function
- **Colours and sizes:** the CSS variables at the top of the stylesheet; the clock is sized in `em`, so changing `font-size` on `.clock` scales the whole thing

## Credits and licence

Unofficial fan project, not affiliated with Vsauce, The Curiosity Box or Inq Factory. The Death Clock concept and name belong to their creators. Fonts (Barlow Condensed and IBM Plex Mono) are loaded from Google Fonts under the SIL Open Font License.

Released under the MIT License.

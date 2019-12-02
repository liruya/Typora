- Capture with GUI:

  ```
  flameshot gui
  ```

- Capture with GUI with custom save path:

  ```
  flameshot gui -p ~/myStuff/captures
  ```

- Open GUI with a delay of 2 seconds:

  ```
  flameshot gui -d 2000
  ```

- Fullscreen capture with custom save path (no GUI) and delayed:

  ```
  flameshot full -p ~/myStuff/captures -d 5000
  ```

- Fullscreen capture with custom save path copying to clipboard:

  ```
  flameshot full -c -p ~/myStuff/captures
  ```

- Capture the screen containing the mouse and print the image (bytes) in PNG format:

  ```bash
  flameshot screen -r
  ```

- Capture the screen number 1 and copy it to the clipboard:

  ```bash
  flameshot screen -n 1 -c
  ```


xinit
=====

What is x11/xinit?
------------------

The xinit package provides:

    - startx: A script to manually launch Xorg and your window manager (e.g., AwesomeWM).
    - xinit: The core utility to initialize Xorg and start a user-specified session (e.g., `~/.xinitrc`).

Without `xinit`, you cannot start Xorg manually (e.g., via `startx`). However, if you are only using a login manager (like Slim), `xinit` is not strictly required, but it is still highly recommended for troubleshooting.


Do You Need to Install xinit?
-----------------------------

Yes! Here is why:

    - Dependency Check: The xorg meta-package on FreeBSD does not include `xinit` by default. You must install it separately.
    - Troubleshooting: If Slim fails, `startx` lets you test Xorg/AwesomeWM directly.
    - Flexibility: Required for customizing startup scripts (e.g., `~/.xinitrc`).


Key Notes
---------

Slim vs. startx:

    - Slim automatically launches Xorg and your WM.
    - startx is only needed if you bypass Slim (e.g., startx awesome).

Configuration:

If you use startx, create/update `~/.xinitrc` to launch AwesomeWM:

```sh
echo "exec awesome" > ~/.xinitrc
```
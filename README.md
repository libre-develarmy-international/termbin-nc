# termbin-nc

Upload command output to [termbin.com](https://termbin.com) \
using \
  
[netcat](https://en.wikipedia.org/wiki/Netcat).

`termbin-nc` reads data from standard input and prints the generated
Termbin URL.

## Requirements

- Bash
- Netcat (`nc`)
- An internet connection

No additional dependencies or installation steps are required beyond Bash
and Netcat.

Check whether Netcat is available:

```bash
command -v nc
```

If this command prints a path such as `/usr/bin/nc`, Netcat is installed.

## Usage

Make the script executable:

```bash
chmod +x termbin-nc
```

Pipe command output to `termbin-nc`:

```bash
lsusb | ./termbin-nc
```

Upload the contents of a file:

```bash
cat ~/.bashrc | ./termbin-nc
```

Alternatively, use input redirection:

```bash
./termbin-nc < ~/.bashrc
```

Upload output from other commands:

```bash
journalctl -b | ./termbin-nc
```

```bash
dmesg | ./termbin-nc
```

```bash
printf 'Hello, Termbin!\n' | ./termbin-nc
```

The command prints a URL similar to:

```text
https://termbin.com/abc123
```

## Options

```text
-h, --help       Display the help message and exit
    --version    Display version information and exit
```

Examples:

```bash
./termbin-nc --help
./termbin-nc --version
```

## Security Notice

Do not upload passwords, private keys, API tokens, personal information, or
other sensitive data. The input is transmitted to the Termbin service.


## Author

[develarmy.org](https://develarmy.org)

## License

Copyright (C) 2026 develarmy.org

This project is licensed under the
[GNU General Public License v3.0 or later](https://www.gnu.org/licenses/gpl-3.0.html).

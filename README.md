# CDPwn

This Python script is designed to capture screenshots of files via the Chrome DevTools Protocol (CDP), a technique useful for privilege escalation when the CDP service runs with root permissions 🛡️. The script leverages the `pycdp` library to interact with CDP and the `pwn` library to manage network connections. This functionality is particularly advantageous for gaining higher-level access to systems where CDP runs with elevated privileges 🔒.

## Dependencies 📦

- `argparse`: Standard library for parsing command-line arguments.
- `asyncio`: Standard library for handling asynchronous I/O operations.
- `base64`: Standard library for encoding and decoding binary data.
- `pycdp`: Third-party library for interfacing with the Chrome DevTools Protocol. Available at https://github.com/HMaker/python-cdp. Note: You may need to modify `target.py` within this library, for instance, changing `can_access_opener=bool(json['canAccessOpener']),` to `can_access_opener=bool(json['canAccessOpener'],False),`.
- `pwn`: Third-party library for simplifying the creation and manipulation of network connections.

## Command-Line Arguments 💻

`cdpwn.py` accepts the following command-line arguments:

- `-i` or `--ip` 📶: Required. IP address to connect to.
- `-p` or `--port` 🔌: Required. Port to connect to.
- `-f` or `--file` 📂: Required. File to navigate to.
- `-s` or `--screenshot` 📸: Optional. Name of the screenshot file. Defaults to 'screenshot.png' if not specified.

## Usage Examples 🚀

To capture a screenshot from a local CDP server running at IP address `127.0.0.1` on port `46717`, and navigate to `/root/.ssh/id_rsa`, use the following command:

```python
python cdpwn.py -i 127.0.0.1 -p 46717 -f /root/.ssh/id_rsa
```

This command will generate a screenshot file named 'screenshot.png' in the same directory as the script.

**Note:** The script uses the `file://` protocol to navigate to the specified file, which should be located on the server that the script connects to.

## How to Contribute

If you're interested in contributing to the project or have any feedback on these planned features and proposed improvements, please feel free to:

1. Select a feature or improvement from the list above that you'd like to work on or provide feedback on.
2. Fork the project repository to your GitHub account.
3. Create a new branch for your work based on the `master` branch.
4. Implement the feature or improvement in your branch.
5. Submit a pull request to the main repository's `master` branch.
6. Collaborate with project maintainers and other contributors to review and iterate on your changes until they're ready to be merged.

Your contributions and feedback are highly appreciated and will help make the project better for everyone!

## License

This project is licensed under the MIT License - see the LICENSE file for details.

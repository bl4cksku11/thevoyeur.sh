# SHODAN ASSET ENUMERATOR
by bl4cksku11

 Short description:
   Simple Bash tool that enumerates a list of IPs / hostnames using the
   Shodan CLI. Loads assets from a file (comma-separated or newline),
   queries `shodan host` for each asset, and writes results to a
   timestamped output file.

 Features:
   - Verifies presence of the Shodan CLI and prompts to install if missing.
   - Initializes Shodan API key (uses ~/.config/shodan/api_key or runs `shodan init`).
   - Accepts asset lists in two formats:
       1) Comma-separated single line:  1.2.3.4,5.6.7.8,example.com
       2) One asset per line:
            1.2.3.4
            example.com
   - Queries Shodan for each asset with `shodan host <asset>` and saves
     the pretty-formatted output to a file: shodansearch-YYYYMMDD-HHMMSS.txt
   - Provides friendly output messages and graceful Ctrl+C handling.

 Usage:
   1. Ensure Shodan CLI is installed: `pip install shodan`
   2. Ensure your Shodan API key is initialized:
        - Place key at $HOME/.config/shodan/api_key
        - or let the script run `shodan init` and enter your key when prompted
   3. Run the script and provide the asset file name when asked.

 Examples of valid asset files:
   Comma-separated:
     111.222.111.222,222.222.111.111,example.com

   Newlines:
     111.222.111.222
     222.222.111.111
     example.com

 Output:
   - A timestamped file named shodansearch-YYYYMMDD-HHMMSS.txt will contain
     the `shodan host` pretty output for each queried asset.

 Notes & Responsible Use:
   - Only query hosts and networks for which you have explicit permission.
   - Misuse of Shodan/host scanning against third-party infrastructure
     may violate laws, terms of service or client agreements.
   - This script is provided as-is. Verify behavior in a safe/test environment.

 Requirements:
   - bash (tested on common Linux environments)
   - shodan CLI (installable via pip: `pip install shodan`)
   - Network connectivity to Shodan API

 Contact / Author:
   - bl4cksku11


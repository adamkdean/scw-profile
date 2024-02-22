# SCW Profile Manager

The SCW Profile Manager is a Bash script designed to facilitate the management and switching of profiles for the [Scaleway CLI](https://www.scaleway.com/en/cli/) tool. This utility allows users to easily switch between different Scaleway accounts, ensuring that commands are executed with the correct account credentials without manually exporting environment variables each time.

## Features

- **Profile Switching:** Quickly switch between different Scaleway profiles, each with its own set of credentials and settings.
- **Environment Setup:** Automatically configures the environment with the necessary credentials for the active profile.
- **Profile Listing:** Displays all available profiles, highlighting the currently active profile.
- **Easy Integration:** Works seamlessly with the existing Scaleway CLI, enhancing its functionality without modifying its core behavior.

## Installation and Setup

### Prerequisites

- Scaleway CLI installed (`scw`)
- `jq` installed for JSON processing

- **Caveat:** The script assumes that `scw` was installed via Homebrew and thus sets `SCW_BINARY=/opt/homebrew/bin/scw`. If your installation path is different, please update this variable in the script accordingly.

### Installation Steps

1. **Create the Profiles File:** Create a JSON file at `~/.scw_profiles.json` with your Scaleway profiles. Here's an example structure:

```json
{
  "example1": {
    "SCW_ACCESS_KEY": "SCWXXXXXXXXXXXXXXXXX",
    "SCW_SECRET_KEY": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "SCW_DEFAULT_ORGANIZATION_ID": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "SCW_DEFAULT_PROJECT_ID": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  },
  "example2": {
    "SCW_ACCESS_KEY": "SCWYYYYYYYYYYYYYYYYY",
    "SCW_SECRET_KEY": "yyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy",
    "SCW_DEFAULT_ORGANIZATION_ID": "yyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy",
    "SCW_DEFAULT_PROJECT_ID": "yyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy"
  }
}
```

2. **Download and Configure the Script:** Save the script to a preferred location, such as `/usr/local/bin/scw`, and ensure it is executable:

```bash
chmod +x /usr/local/bin/scw
```

3. **Use the SCW Profile Manager:** Ensure your terminal sources the script correctly. You might need to adjust your `PATH` environment variable or create an alias.

### Usage

- **Switch Profile:** Switch to a specific profile.

```bash
scw profile switch <profile_name>
```

- **List Profiles:** List all available profiles, with the active profile indicated.

```bash
scw profile list
```

- **Current Profile:** Display the currently active profile.

```bash
scw profile current
```

- **Pass-through Commands:** Any other command is passed through to the original `scw` binary.

```bash
scw <command>
```

## Utility Explanation

This tool enhances the Scaleway CLI by introducing profile management, making it effortless to switch between different sets of credentials. It's particularly useful for developers and system administrators managing resources across multiple Scaleway accounts.

## License

This software is released under the GPL-3.0 license. A copy of the license can be found in the LICENSE file.

---

Ensure to replace placeholders like `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx` with your actual Scaleway credentials. This documentation provides a comprehensive guide to installing, configuring, and using the SCW Profile Manager to enhance your Scaleway CLI experience.

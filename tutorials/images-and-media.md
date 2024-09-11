---
description: Installation Guide for MLO Files on QB Core Server
cover: ../.gitbook/assets/1 (1).png
coverY: 0
---

# INSTALLATION

This guide provides a comprehensive, step-by-step process for installing MLO (Map Location Object) files on your QB Core server. Follow these instructions carefully to ensure a successful setup.

## Prerequisites

* **QB Core Server**: Ensure you have a functioning QB Core server setup.
* **MLO File**: Obtain the MLO file you wish to install.
* **FiveM Resources Folder**: Access to your server’s resources directory.

## Step-by-Step Installation

1. **Prepare Your Environment**

* **Backup Your Server**: Before making any changes, backup your server files to prevent data loss.
* **Ensure Compatibility**: Verify that the MLO file is compatible with your version of QB Core and FiveM.

2. **Download and Extract MLO Files**

* **Download the MLO File**: Obtain the MLO file package from your source.
* **Extract the Files**: Use a file extraction tool to unzip the MLO file package. You should see a folder containing the MLO files, such as `.ydr`, `.yft`, and `.yft`.

3. **Add MLO Files to Your Resources Folder**

* **Navigate to Your Resources Folder**:
  * Locate your FiveM server’s `resources` directory. This is usually found in the root directory of your server files.
* **Create a New Resource Folder**:
  * Inside the `resources` directory, create a new folder for your MLO file. Name it appropriately (e.g., `mlo_example`).
* **Move MLO Files**:
  * Copy the extracted MLO files into the newly created folder.

4. **Configure the Resource**

**Create a `__resource.lua` File**:

* In the MLO folder, create a file named `__resource.lua`.
* Add the following content to the `__resource.lua` file

```
-- Resource Manifest Version
fx_version 'cerulean'
game 'gta5'

-- Data Files
data_file 'DLC_ITYP_REQUEST' 'stream/[your_file_name].ytyp'

```

* Replace `[your_file_name]` with the name of your MLO file.
* **Create a `fxmanifest.lua` File**:
  * Alternatively, if you’re using the latest FiveM standards, create a `fxmanifest.lua` file in the same directory.
  * Add the following content:

```
-- Resource Manifest Version
fx_version 'cerulean'
game 'gta5'

-- Define the resource
files {
    'stream/[your_file_name].ydr',
    'stream/[your_file_name].yft',
    'stream/[your_file_name].yft'
}

data_file 'DLC_ITYP_REQUEST' 'stream/[your_file_name].ytyp'

```

* Replace `[your_file_name]` with the appropriate filenames for your MLO files.

**5. Update `server.cfg`**

* **Open `server.cfg`**:
  * Locate and open your server’s `server.cfg` file using a text editor.
* **Add the MLO Resource**:
  * Add the following line to ensure your server loads the MLO resource

```
ensure mlo_example
```

* Replace `mlo_example` with the folder name you created for the MLO file.

**6. Start Your Server**

* **Restart Your Server**:
  * Save all changes and restart your FiveM server to apply the new resource.
* **Verify Installation**:
  * Join your server and verify that the MLO is loaded correctly. Check for any errors in the console and ensure the MLO appears as expected in the game.

**7. Troubleshooting**

* **Check Console for Errors**: Look for any error messages in the server console related to the MLO resource.
* **Verify File Paths**: Ensure that all file paths and names in the configuration files are correct.
* **Consult Documentation**: Refer to the MLO file’s documentation for any specific setup instructions or requirements.



## Additional Resources

* **FiveM Documentation**: [FiveM Documentation](https://docs.fivem.net/docs/)
* **QB Core Documentation**: [QB Core Documentation](https://docs.qbcore.org/qbcore-documentation)

For further assistance, feel free to reach out through our support channels or [<mark style="color:orange;">**Discord**</mark>](https://discord.gg/bHyRDuYqpB).

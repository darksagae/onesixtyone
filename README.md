# onesixtyone
`onesixtyone` is a command-line tool used for SNMP (Simple Network Management Protocol) enumeration. It helps discover devices on a network and can be used to identify potential vulnerabilities by querying SNMP-enabled devices.

### Installation

`onesixtyone` is typically pre-installed in Kali Linux. If it's not installed, you can use the following command:

```bash
sudo apt-get install onesixtyone
```

### Basic Command Structure

The basic syntax for using `onesixtyone` is:

```bash
onesixtyone -c <community_string_file> -i <target_file>
```

### Common Options

- `-c <community_string_file>`: Specify a file containing the SNMP community strings to test.
- `-i <target_file>`: Specify a file containing the target IP addresses.
- `-p <port>`: Specify the port number (default is 161).

### Example Usage

1. **Create a Community String File**:
   First, create a file named `community.txt` with potential community strings, for example:

   ```
   public
   private
   secret
   ```

2. **Create a Target File**:
   Create a file named `targets.txt` with the target IP addresses, for example:

   ```
   192.168.1.1
   192.168.1.2
   ```

3. **Running `onesixtyone`**:
   Run the following command to enumerate SNMP information:

   ```bash
   onesixtyone -c community.txt -i targets.txt
   ```

### Expected Output

The output will display the results of the SNMP enumeration, indicating which community strings were successful for each target. For example:

```
192.168.1.1: public
192.168.1.2: private
```

### Conclusion

`onesixtyone` is a powerful tool for SNMP enumeration, allowing you to identify devices and their configurations on a network. Always ensure you have permission before scanning any network.





                                            ALTERNATIVE
`onesixtyone` is a network scanner used for enumerating SNMP (Simple Network Management Protocol) services on a network. It can identify devices and retrieve information such as community strings.

### How to Use `onesixtyone`

1. **Installation**: If not already installed, you can typically install it using:
   ```bash
   sudo apt-get install onesixtyone
   ```

2. **Basic Command Structure**:
   The basic syntax for using `onesixtyone` is:
   ```bash
   onesixtyone -c <community_list> -i <target_ip>
   ```

### Common Options

- `-c <community_list>`: Specify a file containing a list of community strings.
- `-i <target_ip>`: Specify the target IP address or range.
- `-p <port>`: Specify the SNMP port (default is 161).
- `-o <output_file>`: Save results to a specified output file.

### Example Usage

1. **Basic SNMP Enumeration**:
   To perform a basic SNMP enumeration:
   ```bash
   onesixtyone -c communities.txt -i 192.168.1.1
   ```

   **Expected Output**:
   ```
   192.168.1.1:161  public
   192.168.1.1:161  private
   ```

2. **Using a Specific Port**:
   If the SNMP service is running on a non-default port:
   ```bash
   onesixtyone -c communities.txt -i 192.168.1.1 -p 162
   ```

   **Expected Output**:
   ```
   192.168.1.1:162  public
   192.168.1.1:162  private
   ```

### Conclusion

`onesixtyone` is a powerful tool for SNMP enumeration, allowing you to discover devices and community strings on a network. Always ensure you have permission to scan the target network.






                            ALTERNATIVE
Understood. Let me provide information on the `onesixtyone` tool in Kali Linux.

`onesixtyone` is a simple SNMP (Simple Network Management Protocol) scanner that can be used to discover SNMP-enabled devices on a network and attempt to enumerate their management information base (MIB) data.

### How to Use `onesixtyone`

1. **Installation**: `onesixtyone` is typically pre-installed in Kali Linux. If not, you can install it using:

   ```
   sudo apt-get install onesixtyone
   ```

2. **Basic Command Structure**:
   The basic syntax for using `onesixtyone` is:

   ```
   onesixtyone <target_ip_address> <community_string>
   ```

   Here, `<target_ip_address>` is the IP address of the device you want to scan, and `<community_string>` is the SNMP community string to use (often "public" or "private").

### Example Usage

1. **Scanning a Single IP Address**:
   ```
   onesixtyone 192.168.1.100 public
   ```

   **Expected Output**:
   ```
   192.168.1.100 [public] open
   ```

   This command will scan the device at IP address `192.168.1.100` using the "public" community string.

2. **Scanning a Range of IP Addresses**:
   ```
   onesixtyone 192.168.1.1-254 public
   ```

   **Expected Output**:
   ```
   192.168.1.1 [public] open
   192.168.1.100 [public] open
   192.168.1.254 [public] open
   ```

   This command will scan the entire `192.168.1.0/24` subnet using the "public" community string.

3. **Scanning with a Custom Community String**:
   ```
   onesixtyone 192.168.1.100 myCustomString
   ```

   **Expected Output**:
   ```
   192.168.1.100 [myCustomString] open
   ```

   This command will scan the device at IP address `192.168.1.100` using the custom community string "myCustomString".

### Conclusion

`onesixtyone` is a simple yet effective tool for discovering SNMP-enabled devices on a network and attempting to enumerate their MIB data. It can be a useful tool for network discovery and potentially identifying vulnerabilities. As always, ensure you have permission before scanning any devices.



                                          ALTERNATIVE
`onesixtyone` is a command-line tool used for SNMP (Simple Network Management Protocol) enumeration. It's designed to quickly determine the SNMP community string of a target device. Here's how to use it, along with examples and expected outputs:

### How to Install `onesixtyone`

If `onesixtyone` is not already installed on your Kali Linux system, you can install it using the following command:

```bash
sudo apt-get install onesixtyone
```

### Basic Usage and Examples

1.  **Basic Scan:**

    To perform a basic scan against a target IP address or hostname using the default community string list, use the following command:

    ```bash
    onesixtyone <target IP or hostname>
    ```

    For example:

    ```bash
    onesixtyone 192.168.1.1
    ```

    This command attempts to determine the SNMP community string of the device at 192.168.1.1.

2.  **Specifying a Custom Community String List:**

    You can specify a custom list of community strings to use during the scan with the `-c` option:

    ```bash
    onesixtyone -c <path_to_community_list_file> <target IP or hostname>
    ```

    For example:

    ```bash
    onesixtyone -c /usr/share/wordlists/snmp.txt 192.168.1.1
    ```

    This command uses the community strings listed in `/usr/share/wordlists/snmp.txt` to scan the target device.

3.  **Specifying SNMP Version:**

    You can specify the SNMP version to use. By default, `onesixtyone` uses SNMPv1. To specify SNMPv2c, use the `-2c` option:

    ```bash
    onesixtyone -2c <target IP or hostname>
    ```

    For example:

    ```bash
    onesixtyone -2c 192.168.1.1
    ```

    This command uses SNMPv2c to scan the target device.

4.  **Using Specific Timeout and Retries:**

    You can set a timeout value using the `-t` option and the number of retries using the `-r` option:

    ```bash
     onesixtyone -t <timeout_value> -r <number_of_retries> <target IP or hostname>
    ```

    For example:

    ```bash
    onesixtyone -t 1 -r 3 192.168.1.1
    ```

    This command sets the timeout to 1 second and the number of retries to 3.

### Expected Output

The output from `onesixtyone` will vary depending on whether a valid community string is found. Here are a couple of examples:

1.  **Successful Scan (Community String Found):**

    If a valid community string is found, the output will look something like this:

    ```text
    192.168.1.1: public
    ```

    This indicates that the community string "public" is valid for the device at 192.168.1.1.

2.  **Unsuccessful Scan (No Community String Found):**

    If no valid community string is found, the output will typically show nothing, or it might display timeout messages if the target does not respond.

    ```text
    Timeout: 192.168.1.1
    ```

### Important Notes

*   Ensure you have permission to scan the target device. Unauthorized scanning can be illegal and unethical.
*   The effectiveness of `onesixtyone` depends on the strength and variety of community strings used. Using a comprehensive wordlist will increase the chances of finding the correct community string.
*   SNMP enumeration can provide valuable information about a target device, so it's important to secure your own devices by changing the default community strings and restricting access to SNMP services.





                               ALTERNATIVE
Onesixtyone is a Kali Linux tool used for identifying SNMP (Simple Network Management Protocol) devices on a network. It can be used to scan a network for devices that respond to SNMP requests, and can also be used to brute-force SNMP community strings.

**How to Use Onesixtyone**

The basic syntax for using onesixtyone is:
```
onesixtyone [options] <target>
```
Here, `<target>` is the IP address or hostname of the device or network you want to scan.

**Common Options**

- `-c`: Specify the community string to use (e.g., `public`).
- `-i`: Specify the input file containing a list of community strings to try.
- `-o`: Specify the output file to write the results to.
- `-t`: Specify the timeout in seconds (default is 5).

**Example Usage**

1. **Basic Scan**:
```
onesixtyone 192.168.1.100
```
This will scan the device at `192.168.1.100` for SNMP devices using the default community string `public`.

**Expected Output**:
```
Scanning 192.168.1.100

SNMPv1 server at 192.168.1.100
  System desc: Linux 3.10.0-957.el7.x86_64
  System contact: Root <root@localhost>
  System name: localhost.localdomain
```
2. **Brute-Forcing Community Strings**:
```
onesixtyone -i community_strings.txt 192.168.1.100
```
This will scan the device at `192.168.1.100` using a list of community strings from the file `community_strings.txt`.

**Expected Output**:
```
Scanning 192.168.1.100

Trying community string 'private'
  SNMPv1 server at 192.168.1.100
  System desc: Linux 3.10.0-957.el7.x86_64
  System contact: Root <root@localhost>
  System name: localhost.localdomain
```
Remember to use onesixtyone responsibly and only with permission from the system owner or administrator.




                                            

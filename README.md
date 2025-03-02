# JSBucket: S3 Bucket Discovery Tool From JavaScript Files

`JSBucket` is a Python-based tool designed to analyze subdomains for Amazon S3 bucket references in JavaScript files. It extracts S3 bucket names and URLs from subdomains and outputs them in a structured JSON format. The tool supports multi-threading, progress tracking, and silent mode for seamless integration with other tools like `jq`, `s3scanner`, etc. This tool is specifically designed for **Bug Bounty Hunters** and **Pentesters**.

---

## Features ⚙️

```shell
usage: jsbucket [-h] [-u SUBDOMAIN] -d DOMAIN [-l LIST] [-t THREADS] [-timeout TIMEOUT] [-o OUTPUT] [-silent]

Analyze JavaScript files from given subdomain(s) for S3 buckets.

options:
  -h, --help            Show this help message and exit
  -u SUBDOMAIN, --subdomain SUBDOMAIN
                        Analyze a single subdomain (e.g., `sub.example.com`)
  -d DOMAIN, --domain DOMAIN
                        Base/root domain (mandatory)
  -l LIST, --list LIST  File containing a list of subdomains (one per line)
  -t THREADS, --threads THREADS
                        Number of threads for concurrent analysis (default: 10)
  -timeout TIMEOUT      Timeout for HTTP requests (default: 10 seconds)
  -o OUTPUT, --output OUTPUT
                        Save results to a JSON file (e.g., `output.json`)
  -silent               Suppress all output except raw JSON (useful for piping into tools like `jq` or `grep`)
```

---

## Installation 🚀

### Prerequisites
1. **Python 3.6+**: Ensure Python is installed on your system.
2. **Dependencies**: Install the required libraries using `pip`.

### Steps
```bash
git clone https://github.com/saeed0xf/jsbucket.git
cd jsbucket
pip install -r requirements.txt
```

Alternatively, you can install the tool directly from PyPI:
```bash
pip install jsbucket
```

---

## Usage 📝

Run the script with the desired flags:

```bash
jsbucket [FLAGS]
```

---

## Flags

| Flag            | Description                                                                                   |
|------------------|-----------------------------------------------------------------------------------------------|
| `-u SUBDOMAIN`   | Analyze a single subdomain (e.g., `sub.example.com`).                                          |
| `-d DOMAIN`      | Base/root domain (mandatory).                                                                 |
| `-l FILE`        | File containing a list of subdomains (one per line).                                           |
| `-t THREADS`     | Number of threads for concurrent analysis (default: 10).                                      |
| `-timeout SECS`  | Timeout for HTTP requests (default: 10 seconds).                                              |
| `-o OUTPUT`      | Save results to a JSON file (e.g., `output.json`).                                            |
| `-silent`        | Suppress all output except raw JSON (useful for piping into tools like `jq` or `grep`).       |

---

## Examples 🕵️‍♀️

### 1. Analyze a Single Subdomain
```bash
jsbucket -u sub.example.com -d example.com
```

### 2. Analyze a List of Subdomains
```bash
jsbucket -l subdomains.txt -d example.com
```

### 3. Save Results to a JSON File
```bash
jsbucket -l subdomains.txt -d example.com -o results.json
```

### 4. Use Silent Mode for Piping
```bash
jsbucket -l subdomains.txt -d example.com -silent | jq '.[].s3_buckets[].bucket_name'
```

### 5. Customize Threads and Timeout
```bash
jsbucket -l subdomains.txt -d example.com -t 20 -timeout 30
```

---

## Output Format

### Terminal Output (Non-Silent Mode)
```plaintext
Alert: S3 Bucket(s) found on subdomain https://sub.example.com!
{
  subdomain: https://sub.example.com,
  s3_buckets: [
    {
      bucket_name: my-bucket,
      bucket_url: https://my-bucket.s3.amazonaws.com
    }
  ]
}

✅ Analysis complete!
```

### JSON Output (Silent Mode)
```json
[
  {
    "subdomain": "https://sub.example.com",
    "s3_buckets": [
      {
        "bucket_name": "my-bucket",
        "bucket_url": "https://my-bucket.s3.amazonaws.com"
      }
    ]
  }
]
```

---

## Notes 📌

1. **Silent Mode**: Use the `-silent` flag when integrating with tools like `jq` or `s3scanner`. This ensures only raw JSON is printed to `stdout`.
2. **Timeout**: Adjust the `-timeout` value if subdomains take longer to respond.
3. **Threads**: Increase the `-t` value for faster analysis, but be cautious with high thread counts to avoid overwhelming the network or server.

---
<<<<<<< HEAD

## Contributing 🤝

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to:
- Open an issue.
- Submit a pull request.

---

## License 📜

This project is licensed under the [MIT License](https://github.com/saeed0xf/jsbucket/blob/main/LICENSE). See the `LICENSE` file for details.
=======
## Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

---
## License
This project is licensed under the [MIT License](https://github.com/saeed0xf/jsbucket/blob/main/LICENSE). See the LICENSE file for details.
>>>>>>> e1deb308fdd2381725d6cc774ff5aefc2d05d87b

---

## Contact 💻

For questions, suggestions, or feedback, feel free to reach out:
<<<<<<< HEAD

- Twitter/X: [@Saeed0x1](https://x.com/saeed0x1)
- LinkedIn: [Saeed0x1](https://www.linkedin.com/in/saeed0x1)
- GitHub: [saeed0xf](https://github.com/saeed0xf)
=======
- Twitter/X: [Saeed0x1](https://x.com/saeed0x1)
- Linkedin: [Saeed0x1](https://www.linkedin.com/in/saeed0x1) 
- GitHub: [saeed0xf](https://github.com/saeed0xf)
>>>>>>> e1deb308fdd2381725d6cc774ff5aefc2d05d87b

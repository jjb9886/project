import requests
import time

urls = [
    "http://52.214.255.185/",
    "http://rte.ie",
    "http://amazon.ie"
]

max_retries = 3
retry_delay = 5

for url in urls:
    print(f"Checking {url}...")
    for attempt in range(1, max_retries + 1):
        try:
            response = requests.get(url, timeout=5)
            if response.status_code == 200:
                print(f"{url} is up")
                break
            else:
                print(f"{url} issue detected - Status code: {response.status_code}")
                break
        except requests.exceptions.RequestException as e:
            print(f"Attempt {attempt} for {url} failed: {e}")
            if attempt < max_retries:
                print(f"Retrying in {retry_delay} seconds...")
                time.sleep(retry_delay)
            else:
                print(f"Max retries reached. {url} is unreachable.")
    print("-" * 40)  # Separator for readability


import requests

TOKEN = <enter token here>
INFLUX_URL = "http://localhost:8086/api/v2/write"
ORG = "test"
BUCKET = "Carolina-Code-Conference-Bucket"

#Before second run: Comment this out in order to default to nanosecond precision
PRECISION = "s"

#before second run, change the measurement
line = "bar,tag1=productA cpu_pct=91.1 1755055153"


params = {
    "org": ORG,
    "bucket": BUCKET,
    "precision": PRECISION
}

headers = {
    "Authorization": f"Token {TOKEN}",
    "Content-Type": "text/plain; charset=utf-8"
}

response = requests.post(
    url=INFLUX_URL,
    params=params,
    headers=headers,
    data=line
)

print(f"Status Code: {response.status_code}")
print(f"Response Body: {response.text or '<no content>'}")

## Terminal Command --> influx query 'from(bucket:"Carolina-Code-Conference-Bucket") |> range(start:-2880m)'

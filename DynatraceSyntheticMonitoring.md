# Synthetic Monitoring

# Go to Synthetic Monitoring

<img width="1432" height="898" alt="image" src="https://github.com/user-attachments/assets/b27cbb77-cf9f-41f6-afa6-6faeb2456a30" />

# Click on HTTP

<img width="517" height="283" alt="image" src="https://github.com/user-attachments/assets/622c3135-50bd-44e7-afc9-c0cb772cce48" />

# Create HTTP monitor / General

<img width="1341" height="531" alt="image" src="https://github.com/user-attachments/assets/67132f22-67e9-4bf1-a970-7288a3a2b73d" />

# steps

<img width="1601" height="860" alt="image" src="https://github.com/user-attachments/assets/3bd6416a-6e8f-47c2-aa9b-2910a3f12093" />

# Frequency and locations (Select india region / whole world)

<img width="1363" height="803" alt="image" src="https://github.com/user-attachments/assets/4a2c40b6-213c-4366-a29f-a4a4de432ff4" />

<img width="985" height="163" alt="image" src="https://github.com/user-attachments/assets/aa0475a5-2f08-4494-bfea-8b50c0927a4c" />

# Outage and performance

<img width="1299" height="545" alt="image" src="https://github.com/user-attachments/assets/dc5a3d8b-136e-47fb-ae92-16dfb015ffa1" />

# Summary

<img width="1287" height="767" alt="image" src="https://github.com/user-attachments/assets/05c43e31-eb80-436a-b973-b019566a9e31" />

# Synthetic Monitoring (the clean, Dynatrace-native way)

This is the recommended approach.

You’re not generating “fake users”, you’re creating a controlled synthetic probe.

What this gives you

Availability (up/down)

Response time

HTTP status codes

Network timing (DNS, TCP, SSL)

Visibility even when no real users exist

## Step-by-step in Dynatrace UI

1. Log in to Dynatrace

2. Go to Observe & Explore → Synthetic

3. Click Create a synthetic monitor

Choose HTTP monitor

## Configure:

URL: http://136.115.5.255/

Name: Prod-IP-Availability-Test

Frequency: every 5 minutes (start slow)

Locations: choose at least one public location

Save and start the monitor

What to watch after it runs

In Dynatrace you’ll see:

Availability %

Response time trends

HTTP failures (4xx / 5xx)

Network breakdown

This is safe, auditable, and production-approved.

Method B: Generate traffic from server + observe in Dynatrace

Use this only if:

OneAgent is installed on the server

You want to see service flow / PurePath traces

From a Linux machine (controlled test)
ab -n 200 -c 10 http://136.115.5.255/


Very small load. Enough to create traces.

What you’ll see in Dynatrace

If OneAgent is active:

Service detected

Incoming requests

Response time

CPU / memory correlation

PurePath traces

If you see nothing, it means:

OneAgent not installed

Traffic not hitting an instrumented service

Firewall blocking

Which method should you choose?

Use this rule:

✅ Website availability / uptime → Synthetic Monitor

✅ App performance & code-level tracing → OneAgent + traffic

❌ Random traffic generators → never in production

Very important production rule

Do NOT:

Run high concurrency tests on a raw IP

Spike traffic without approval

Treat load testing as monitoring

Synthetic monitoring ≠ load testing
Load testing ≠ monitoring

They answer different questions.

Mental model (this matters in interviews)

Synthetic monitoring asks:
“Is my system reachable and how fast from the outside?”

OneAgent tracing asks:
“What exactly happened inside my system when a request arrived?”

Dynatrace shines when you use both, deliberately.

Your next natural steps could be:

validating the synthetic results

mapping the IP to detected services

setting alert thresholds

correlating synthetic failures with host metrics

That’s where observability stops being dashboards and starts being understanding.







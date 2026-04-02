\---

title: "Lessons from My Semester 4 IoT Project"

date: "2026-04-02"

description: "A reflection on building an IoT system with Raspberry Pi, the challenges faced, and solutions implemented."

published: true

tags: \["tech", "coding", "IoT", "Raspberry Pi"]

\---



During my Semester 4 mini project, I worked on an IoT system using a Raspberry Pi. The journey was full of challenges that tested both my technical skills and problem-solving abilities.



\### Hardware Challenges



Acquiring a Raspberry Pi was unexpectedly difficult due to shortages. Multiple trips to Lamington Road yielded no results. Eventually, a contact provided me with a Raspberry Pi with only 512 MB of RAM, which was far from ideal but usable for our project.



\### Initial Approach: Node.js and HTTP Endpoints



Our first implementation used Node.js to create a server on the Raspberry Pi with HTTP endpoints. Devices on the same network could send data successfully. However, displaying this data in a browser, whether Chromium or Firefox, proved impossible due to RAM limitations. Running both a web server and a browser on the 512 MB Raspberry Pi caused severe performance issues. 



\### Flutter App Development



To bypass browser limitations, we developed a Flutter mobile app. Building the app came with its own challenges, particularly handling unusual property behaviors and XML-based data structures. Once the Flutter app could send data over HTTP, we attempted to create a local Wi-Fi access point on the Raspberry Pi so that any nearby device could communicate directly. This approach failed because enabling the access point disrupted SSH access and network stability. The Node.js server also lagged under these conditions, making troubleshooting difficult.



\### Switching to Python



To overcome memory and performance constraints, I switched to Python using lightweight libraries such as `Flask` for the server and `ffmpeg-python` for multimedia handling. Python proved far more efficient in RAM usage and allowed us to reliably send text, images, and video from the Raspberry Pi to the Flutter app. Initially, I had avoided Python due to concerns about CPU usage, but lightweight libraries mitigated this issue.



\### Network Challenges and Cloud Tunneling



The Flutter app worked well when connected to a stable Wi-Fi router. However, in a real-world scenario using a mobile hotspot, HTTP requests failed due to firewall restrictions. To solve this, I used a cloud tunnel service to expose the Raspberry Pi to the internet. I purchased a domain and configured DNS through Cloudflare, forwarding the appropriate port. Once set up, the Raspberry Pi could be accessed from any device over the internet. Bandwidth was limited to 1 GB per month, which was sufficient for our project.



\### Lessons Learned



This project taught me several valuable lessons:



\- Hardware limitations can dictate the choice of software and architecture.

\- Lightweight libraries and Python can outperform Node.js in memory-constrained environments.

\- Real-world network conditions, including firewalls and hotspots, must be considered when designing IoT systems.

\- Flexibility and problem-solving are essential when unexpected issues arise.



Ultimately, the project was a success, not just in terms of functionality, but in the learning gained from overcoming each obstacle. Using Python and cloud tunneling allowed us to achieve a practical and reliable solution, despite the initial hardware and network constraints.  


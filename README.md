## Screenshot 1

![Screenshot 1](
Screenshot_20260725_124505.jpg)
Screenshot_20260725_124505.jpg
DVWA Reflected XSS Page The Reflected XSS module in DVWA was opened in Browser 1. A JavaScript test payload was entered into the vulnerable input field while the application was running on localhost:8080 with the security level set to Low.

Screenshot 2 – Terminal (Netcat Listener) The terminal was configured to monitor incoming HTTP requests using Netcat on port 4444. Apache was restarted successfully, and the listener was started before executing the XSS payload. Commands Used sudo service apache2 restart nc -lvp 4444

Screenshot 3 – Payload Submission (Browser 1) The JavaScript payload was submitted through the vulnerable input field in Browser 1. The application reflected the supplied input back to the browser, allowing client-side JavaScript execution in the local DVWA environment.

Screenshot 4 – Browser 2 (JavaScript Execution) Browser 2 displayed the "XSS Successful" alert dialog, confirming that the injected JavaScript executed successfully. This demonstrates the behavior of a Reflected Cross-Site Scripting vulnerability in a controlled lab environment.

Screenshot 5 – Terminal Request Capture After the JavaScript executed, Browser 2 generated an HTTP request to the Netcat listener. The terminal successfully captured the request and displayed information including: HTTP Method Host Header User-Agent Referer Accept Headers Browser Information This confirmed that the browser communicated with the local listener as expected during the demonstration.

Lab Architecture Browser 1 (DVWA Application) │ │ Submit Payload ▼ DVWA (localhost:8080) │ │ Reflected Response ▼ Browser 2 (JavaScript Executes) │ │ HTTP Request ▼ Netcat Listener (Port 4444) │ ▼ Terminal Logs & HTTP Headers Lab Summary This demonstration was performed using two browser sessions and a Netcat listener. Browser 1 was used to interact with the vulnerable DVWA application, while Browser 2 executed the reflected JavaScript. The terminal monitored and captured the resulting HTTP request, providing visibility into the browser's communication during the Reflected XSS demonstration. All testing was conducted in a local, authorized DVWA lab environment.

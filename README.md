# Repro for issue 10576
### Steps
1. Update Firebase configuration placeholders in `index.html` and enable Anonymous Sign-in method.
2. Serve the `index.html` file using a local web server (e.g., run `npx http-server` in the directory).
3. Open `http://localhost:8080`. Wait for the initial anonymous sign-in to complete and persist in browser storage.
4. Reload the page under normal network conditions. Observe that the load time is very fast (usually < 1 second).
5. Open Chrome DevTools, navigate to the Network tab, and change the throttling profile to Slow 3G.
6. Reload the page again. Observe that the load time increased (2 to 3 seconds).
7. Simulate mobile device environment. Toggle Device Mode in Chrome DevTools and change the dimension to any mobile device.
8. Reload the page again. Observe that the load time significantly increased (> 7 seconds).

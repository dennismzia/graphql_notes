Oauth dirty dancing

## Attack scenario

1. Attacker sends the victim a crafted link that has been prepared to result in a non-happy path in the OAuth-dance.
2. Victim clicks the link. New tab opens up with a sign-in flow with one of the OAuth-providers of the website being exploited.
3. Non-happy path gets triggered on the website being exploited, the vulnerable postMessage-listener is loaded on the page the victim landed on, still with the code or tokens in the URL.
4. Original tab sent by the attacker sends a bunch of postMessages-to the new tab with the website to get the postMessage-listener to leak the current URL.
5. Original tab sent by the attacker then listens to the message sent to it. When the URL comes back in a message, the code and token is extracted and sent to the attacker.
6. Attacker signs in as the victim using the code or token that ended up on the non-happy path.

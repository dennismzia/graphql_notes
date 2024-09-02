# Explains the Secondary context issue in Reverse Proxies.

Technique
- Identify Proxied requests Fuzz with control characters and watch difference in responses
includign headers

- control characters to identify the web root till you get 400 bad request then  go back one directory back till you get 404 not found

- Fuzz for the directories, api docs and other standard fuzzing files 


Rescources
- https://github.com/GrrrDog/weird_proxies
- https://readmedium.com/en/https:/zoidsec.medium.com/path-normalization-crash-course-bc9fa41a0a6e
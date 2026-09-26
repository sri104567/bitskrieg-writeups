Old Sessions - Web exploitation

Approach:

Okay so I started with launching the instance(obviously), it took me to a webpage named The New twitter(http://chatelaine.cylabacademy.net:27200/login)
Next, the hints suggested inspecting and looking at the cookies, so i did that and went to cookies. There, I saw it was completely blank. 
I looked at some of the other stuff too like session and local storage. Nothing was there, so I decided to go on and resgister with my username 
as m1 and password as m2(creative i know) . After that i looked at cookies again, no change. So i decided to login.

Solution:


So after logging in, I saw a change in the cookies section.
<img width="1754" height="1006" alt="Screenshot (51)" src="https://github.com/user-attachments/assets/d8a272d1-01ae-4edf-a6fa-6369a1562bd0" />
Then, I saw one of the comments mentioning /sessions. Initially was very confused and looked everywhere else, then found out its for the web url.
Then i added that in and it gave me this page.
1) session:_iA7EEsRh9VhUuMG0IVSq7soEBU5z75aKuYPpOQwa-k, {'_permanent': True, 'key': 'admin'}

2) session:ESfFsROWs7ir8IUTIUWAePBJ24SaUnpkGtzXABlcsxg, {'_permanent': True, 'key': 'm1'}
   
 So, after this i replaced the text for m1 in cookies to the one for admin and refreshed the page and went back to the normal page and it
showed me the flag.
<img width="1743" height="1014" alt="Screenshot (52)" src="https://github.com/user-attachments/assets/2021425e-538a-4948-aed0-9fed1f45572a" />

Flag:

academy{s3t_s3ss10n_3xp1rat10n5_5337de94}

Takeaway:

First perform the actions written on the screen before checking for the cookies.

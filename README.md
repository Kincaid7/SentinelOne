![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/a31d8d37-1cb8-4cfc-b678-007819d14fa7)

# Introduction
I was one of 5000 participants selected to compete in the inaugural CyberSentinel Capture the Flag (CTF) competition, hosted by Correlation One and the United States Department of Defense. This 8-hour event featured several technical categories and marked my first experience in a CTF competition. Below, I will describe the process I used to navigate the competition and solve some of the challenges.

# Preparation
The day before the competition, I reviewed the resources page on the competition Slack forum, where competitors were sharing various tools and techniques they had used in previous CTF competitions. One participant shared a course he had developed on Udemy called [CTF 101](https://www.udemy.com/course/cyber-ctf-101/), which I quickly enrolled in. This course provided invaluable insights, helping me set up my Kali Linux attack virtual machine with various hacking tools and a foundational understanding of their applications in different challenge categories.

Throughout the competition, I leveraged Google and AI models to assist in solving the challenges. These resources did not solve the challenges for me but suggested various tools and approaches that I could experiment with.

# Printer (Web Security)
This challenge presented a login page. I used DIRB, a command-line tool included in Kali Linux, to scan the webpage for existing and hidden web objects. This scan listed various directories and files, including /robots.txt and /notes.txt. By investigating these files, I found the admin password, logged into the printer, and obtained the flag.

Note: This challenge was problematic due to brute force attempts by other competitors. Despite using the correct credentials, the server repeatedly rejected my login attempts. The developers announced on Slack that the challenge was malfunctioning and advised us to persistently try the correct credentials until the server accepted them. After several minutes of repeated attempts, I successfully logged in and obtained the flag. This issue cost me valuable time, as I had already solved the problem within the first 30 minutes, but spent hours exploring unnecessary rabbit holes due to the server error.

# Header Hinterlands (Network and Recon)
In this challenge, I was given a .tar image to set up a Docker container. Using Google, I learned the specific commands needed to do so. After opening the webpage in my browser and inspecting the source code without finding anything suspicious, I asked ChatGPT for guidance. It recommended using the curl command to fetch the HTTP headers of the webpage. By doing so, I noticed that the X-Syndicate-Command header contained a hash ending with "=", indicating Base64 encoding. I decoded this hash using CyberChef and successfully retrieved the flag.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/065a4cfd-7657-41ff-97f7-0e3108355061)

# Have you bean here before? (OSINT)
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/2a693a39-75f3-434a-9304-083ba38ba780)
This challenge required finding the MAC address for the guest WiFi network at an unknown location. I started by checking the image metadata for geolocation data, which proved unfruitful. I then uploaded the image to Google Lens, but the image was too blurry for Google to recognize any landmarks.

Noticing the name "PAUL" on both the plate and mug, I searched for PAUL Cafe on Google Maps. I found several locations, but based on the surrounding landmarks, I focused on two locations in Washington, D.C. Using Google Street View, I identified the exact location [here](https://www.google.com/maps/@38.90264,-77.0294949,3a,75y,29.05h,90t/data=!3m7!1e1!3m5!1ssBdahcJ2G1T_0CinNOmikg!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DsBdahcJ2G1T_0CinNOmikg%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D10.51405%26pitch%3D0%26thumbfov%3D100!7i16384!8i8192?entry=ttu). I then used [WiGLE](https://wigle.net/map?maplat=38.90274358060917&maplon=-77.02941066978619&mapzoom=21&n=e3%20%2Fmap&coloring=density&rcoisMinimum=0) to identify the PAUL guest network and its MAC address, obtaining the flag. 
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/fc4125fa-8fc4-422a-aa1d-f7d9fe93779c)


# Planes (OSINT)
For this challenge, we were tasked with finding the ICAO airport code of a specific runway, given two images:
![plane](https://github.com/Kincaid7/SentinelOne/assets/41767740/4b7f6b71-0f9c-4d97-b7a9-87df2c451f6a)
![imagery](https://github.com/Kincaid7/SentinelOne/assets/41767740/4933381f-b9a6-4583-978d-6c0d7b1de836)
I started by checking the metadata for additional details but found little information. I then uploaded the images to Google Lens, which led me to a Yahoo [article](https://www.yahoo.com/news/russian-tu-22m3-strategic-bomber-151500879.html) about Russian aircraft and the Soltsy airbase in Russia. However, this airbase did not match the aerial photograph provided.

Narrowing my search to airbases in Russia and Ukraine, I enhanced the aerial photograph using Photoshop and passed the edited photo through Google Lens, which improved the relevancy of the suggested images.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/69606ab2-5cc9-460c-90c3-4297a6788f2b)
After reviewing various suggestions, I found a matching image attached to an X post.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/5c624fb7-2778-4497-8955-85e99ab67c5c)
I then located the ICAO code for the Starokonstantinov airbase on Wikipedia (UKLS) and successfully submitted it as the flag for the challenge.

# Conclusion
Competing in my first CTF competition was an exhilarating experience. It exposed me to a wide variety of tools and techniques that I plan to build upon in future competitions. To continuously improve my skills, I plan to use platforms like TryHackMe and HackTheBox as I advance my career in cybersecurity.

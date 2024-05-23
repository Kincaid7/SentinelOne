![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/a31d8d37-1cb8-4cfc-b678-007819d14fa7)

# Introduction
I was one of 5000 selected to compete in the first CyberSentinel Capture the Flag competition hosted by Correlation One and the United States Department of Defense. It was an 8-hour-long competition with several technical categories. This was my first CTF competition. Below, I will be describing the process I used to navigate the competition and solve some of the challenges.

# Preparation
The day prior to the competition, I checked the resources page on the competition Slack Fourm, where competitors were sharing different tools and techniques they would use in CTF competitions prior. One participant was giving away a course he developed on Udemy called CTF 101, and I hit the jackpot. I enrolled in his course and crammed all its content, resulting in the creation of my Kali Linux attack virtual machine furnished with various hacking tools and a basic understanding as to how and when to use them in various challenge categories.

To aid me throughout the competition, I would utilize Google and AI models to assist in solving the various challenges. These resources did not solve the challenges for me but rather recommended various tools and approaches that I could experiment with.

# Printer (Web Security)
This challenge presented me with a login page. I used a command-line tool called DIRB included in Kali Linux to scan the webpage for existing and hidden web objects. This command scanned the specified webpage and listed various directories and files it found, including /robots.txt and /notes.txt. After investigating the files, I found the admin password and was able to login to the printer and obtain the flag. 

NOTE: This challenge was broken due to brute force attempts by other competitors. Despite the fact that I was using the proper credentials, the server was rejecting my login when it shouldn't have been. The developers announced in Slack that the challenge was misbehaving and recommended continuously trying the correct credentials until the server accepted them. I did this for several minutes, and finally, one login attempt was processed as intended, and I obtained the flag. This error cost me hours of going down rabbit holes when I had already solved the problem in the first 30 minutes, thus reducing the total time I had for other challenges.

# Header Hinterlands (Network and Recon)
In this challenge, I was given a .tar image to set up a docker for. I used Google to learn the specific commands necessary to do so. I then opened the webpage in my browser and looked for some clues. I didn't find anything suspicious and continued to check the source code. Still nothing interesting.
I asked ChatGPT for leads, and it recommended trying the curl command to fetch the HTTP headers of the webpage. I did so and noticed the X-Syndicate-Command contained a hash ending with the characteristic "=" of Base64 encryption. I passed this hash through Cyberchef and was able to decrypt it and find the flag.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/065a4cfd-7657-41ff-97f7-0e3108355061)

# Have you bean here before? (OSINT)
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/2a693a39-75f3-434a-9304-083ba38ba780)
This challenge required finding the MAC address for the guest WiFi network at an unknown location.
To begin, I checked the metadata for the image to see if I could find geolocation data; this was a dead end.
I then uploaded the image to Google Lens and tried searching within the image. However, the image was too blurry for Google to recognize any of the landmarks presented.
Then, seeing that there was coffee and a pastry and that the name PAUL was written on both the plate and mug, I decided to try searching PAUL Cafe on Google Maps. Bingo. While there were several locations, I had a feeling it would be one of the two in Washington based on the surrounding landmarks. Using Google Street View, I found the location [here](https://www.google.com/maps/@38.90264,-77.0294949,3a,75y,29.05h,90t/data=!3m7!1e1!3m5!1ssBdahcJ2G1T_0CinNOmikg!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DsBdahcJ2G1T_0CinNOmikg%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D10.51405%26pitch%3D0%26thumbfov%3D100!7i16384!8i8192?entry=ttu)
I then used [WiGLE](https://wigle.net/map?maplat=38.90274358060917&maplon=-77.02941066978619&mapzoom=21&n=e3%20%2Fmap&coloring=density&rcoisMinimum=0) to identify the PAUL guest network and its MAC address, thus obtaining the flag.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/fc4125fa-8fc4-422a-aa1d-f7d9fe93779c)


# Planes (OSINT)
For this challenge, we were asked to find the ICAO Airport Code of a specific runway. We were given the following images:
![plane](https://github.com/Kincaid7/SentinelOne/assets/41767740/4b7f6b71-0f9c-4d97-b7a9-87df2c451f6a)
![imagery](https://github.com/Kincaid7/SentinelOne/assets/41767740/4933381f-b9a6-4583-978d-6c0d7b1de836)
I began by checking the metadata for additional details, and there was little information to be gained. I then uploaded the images to Google Lens and looked at similar photos. The image of the planes led me to a Yahoo [article](https://www.yahoo.com/news/russian-tu-22m3-strategic-bomber-151500879.html) specifiying Russian aircraft and mentioning Solsty airbase in Russia. Unfortunately, this airbase did not match the aerial photograph provided. This article, however, led me to narrow my search for airbases to Russia and Ukraine. I then tried to find matches for the airport shown in the aerial photograph, but had no luck. Utilizing my background with Photoshop, I applied various enhancements to the aerial shot and passed my edited photo through Google Lens which seemed to improve the relevancy of the suggested images.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/69606ab2-5cc9-460c-90c3-4297a6788f2b)
After combing through the various suggestions, I found a picture attached to an X post that seemed to be an exact match.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/5c624fb7-2778-4497-8955-85e99ab67c5c)
I then located the ICAO code for the Starokonstantinov airbase on Wikipedia (UKLS) and successfully passed it as the flag for the challenge.

# Conclusion
I had a lot of fun competing in my first CTF competition! It was a great exposure to a wide variety of tools and techniques that I will build upon in the next CTF competition come fall. I plan on utilizing sites like TryHackMe and HackTheBox to continuously improve my skills as I advance in my career in Cybersecurity.

![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/a31d8d37-1cb8-4cfc-b678-007819d14fa7)

# Introduction
I was one of 5000 selected to compete in the first CyberSentinel Capture the Flag competition hosted by Correlation One and the United States Department of Defense. It was an 8-hour-long competition with several technical categories. This was my first CTF competition. Below, I will be describing the process I used to navigate the competition and solve some of the challenges.

# Preparation
The day prior to the competition, I checked the resources page on the competition Slack Fourm, where competitors were sharing different tools and techniques they would use in CTF competitions prior. One participant was giving away a course he developed on Udemy called CTF 101, and I hit the jackpot. I enrolled in his course and crammed all its content, resulting in the creation of my Kali Linux attack virtual machine furnished with various hacking tools and a basic understanding as to how and when to use them in various challenge categories.

# Printer (Web Security)
This challenge presented me with a login page. I used a command-line tool called DIRB included in Kali Linux to scan the webpage for existing and hidden web objects. This command scanned the specified webpage and listed various directories and files it found, including /robots.txt and /notes.txt. After investigating the files, I found the admin password and was able to login to the printer and obtain the flag. 

NOTE: Unfortunately, this challenge was broken due to brute force attempts by other competitors. Despite the fact that I was using the proper credentials, the server was rejecting my login when it shouldn't have been. The developers announced in Slack that the challenge was having errors and recommended continuously trying the correct credentials until the application accepted them. I did this for several minutes, and finally, one login attempt was processed as intended, and I obtained the flag. This led to me spending hours going down rabbit holes when I had already solved the problem in the first 30 minutes, and it cost me a lot of time I could have put towards other challenges.

# Header Hinterlands (Network and Recon)

# Have you bean here before? (OSINT)
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/2a693a39-75f3-434a-9304-083ba38ba780)
This challenge required finding the MAC address for the guest WiFi network at an unknown location.
To begin, I checked the metadata for the image to see if I could find geolocation data; unfortunately, this was a dead end.
I then uploaded the image to Google Lens and tried searching within the image. Unfortunately, the image was too blurred for Google to recognize any of the landmarks in the background or the cafe.
Then, seeing that there was coffee and a pastry and that the name PAUL was written on both the plate and mug, I decided to try searching PAUL Cafe on Google Maps. Bingo. While there were several locations, I had a feeling it would be one of the two in Washington based on the surrounding landmarks. Using Google Street View, I found the location [here](https://www.google.com/maps/@38.90264,-77.0294949,3a,75y,29.05h,90t/data=!3m7!1e1!3m5!1ssBdahcJ2G1T_0CinNOmikg!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DsBdahcJ2G1T_0CinNOmikg%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D10.51405%26pitch%3D0%26thumbfov%3D100!7i16384!8i8192?entry=ttu)
I then used [WiGLE](https://wigle.net/map?maplat=38.90274358060917&maplon=-77.02941066978619&mapzoom=21&n=e3%20%2Fmap&coloring=density&rcoisMinimum=0) to identify the PAUL guest network and its MAC address, thus obtaining the flag.
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/fc4125fa-8fc4-422a-aa1d-f7d9fe93779c)


# Planes (OSINT)
<a href="https://example.com" target="_blank">Visit Example</a>




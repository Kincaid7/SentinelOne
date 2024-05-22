![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/a31d8d37-1cb8-4cfc-b678-007819d14fa7)

# Introduction
I was 1 of 5000 selected to compete in the first CyberSentinel Capture the Flag competition hosted by Correlation One and the United States Department of Defense. It was an 8-hour long competition with several technical categories. This was my first CTF competition. Below I will be describing the process I used to navigate the competition and solve some of the challenges.

# Preparation
The day prior to the competition I went onto the Slack for our competition and purused the resources channel. Here competitors were sharing different tools and techniques they would use in CTF competitions prior. One participant was giving away a course he developed on Udemy called CTF 101 and I had hit jackpot. I enrolled in his course and crammed all it's content resulting in the creation of my Kali Linux attack virtual machine furnished with various hacking tools and a basic understanding as to how and when to use them in various challenge categories.

# Printer (Web Security)

# Have you bean here before? (OSINT)
![image](https://github.com/Kincaid7/SentinelOne/assets/41767740/2a693a39-75f3-434a-9304-083ba38ba780)

To begin, I checked the metadata for the image to see if I could find and geolocation data, unfortunately this was a dead end.
I then uploaded the image to Google Lens and tried searching within the image. Unfortunately the image was too blurred for Google to recognize any of the landmarks in the background nor the Cafe.
Then seeing that there was coffee and a pastry, and that the name PAUL was written on both the plate and mug, I decided to try searching PAUL Cafe on Google Maps. Bingo, while there are several locations I had a feeling it would be one of the two in Washington. Using Google Street view, I found the location 
<a href="https://www.google.com/maps/@38.90264,-77.0294949,3a,75y,29.05h,90t/data=!3m7!1e1!3m5!1ssBdahcJ2G1T_0CinNOmikg!2e0!6shttps:%2F%2Fstreetviewpixels-pa.googleapis.com%2Fv1%2Fthumbnail%3Fpanoid%3DsBdahcJ2G1T_0CinNOmikg%26cb_client%3Dmaps_sv.tactile.gps%26w%3D203%26h%3D100%26yaw%3D10.51405%26pitch%3D0%26thumbfov%3D100!7i16384!8i8192?entry=ttu" target="_blank">here</a>
I noticed the “PAUL” on the mug and the surroundings fit a Washington DC looking area. I did a search for a “PAUL” cafe and found 2 separate locations in DC https://www.pauldmv.com/locations/. I then used WiGLE https://wigle.net/map?maplat=38.90289565735777&maplon=-77.02915130976083&mapzoom=18&n=e3%20%2Fmap&coloring=density (had to register) with the address of the Franklin location to identify the PAUL guest network MAC address.

# Planes (OSINT)

# Header Hinterlands (Network and Recon)


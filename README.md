# 💿 Welc♡me to the Groove – Thai Music Collection

A beautiful, responsive web application displaying a curated collection of Thai melodies, featuring immersive audio players, spinning vinyl animations, dynamic polaroid cards, and automatic next-track autoplay functionality.

## 📁 Project Structure

```text
├── index.html          # Portal landing page
├── music.html          # Main dashboard/album hub
├── comfort.html        # Comfort Songs category page
├── tpop.html           # T-Pop Songs category page
├── ost.html            # Original Soundtracks category page
├── gmmtv.html          # GMMTV Series Tracks category page
├── 404.html            # Offline / Error fallback page
└── comfort/            # Directory containing audio assets
    └── [audio files].mp3
```
🚀 Source Code
1. Landing Portal (index.html)
The main entry point featuring a slow-spinning vinyl logo, blurred glass container, and entry prompt.
```text
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welc♡me to the Groove</title>
    <style>
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            overflow: hidden;
            background: url('[https://tse2.mm.bing.net/th/id/OIP.FjgjHCufuCXb86cCEphlwAHaEK?rs=1&pid=ImgDetMain&o=7&rm=3](https://tse2.mm.bing.net/th/id/OIP.FjgjHCufuCXb86cCEphlwAHaEK?rs=1&pid=ImgDetMain&o=7&rm=3)') no-repeat center center fixed;
            background-size: cover;
        }
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.295);
            z-index: -1;
        }
        .welcome-container {
            text-align: center;
            padding: 40px 30px;
            width: 100%;
            max-width: 380px;
            background: rgba(174, 71, 197, 0.4);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 16px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }
        .disc-logo {
            font-size: 100px;
            display: inline-block;
            animation: spin 6s linear infinite;
            margin-bottom: 15px;
        }
        @keyframes spin {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        h1 {
            font-size: 24px;
            color: #ffffff;
            margin: 0 0 25px 0;
            font-weight: bold;
            letter-spacing: 1px;
            line-height: 1.4;
        }
        .enter-btn {
            display: inline-block;
            width: 80%;
            padding: 15px 0;
            background: rgb(161, 34, 178);
            border: 2px solid #ff33ff;
            border-radius: 30px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .enter-btn:hover {
            background: #8613bc;
            box-shadow: 0 0 20px rgba(122, 14, 200, 0.745);
            transform: scale(1.02);
        }
    </style>
</head>
<body>

<div class="welcome-container">
    <div class="disc-logo">💿</div>
    <h1>Welcome to a world of Thai melodies.</h1>
    <a href="music.html" class="enter-btn">Every record has a story.</a>
</div>

<script>
    window.addEventListener("offline", () => {
        window.location.href = "404.html";
    });
</script>
</body>
</html>
```

2. Main Collection Dashboard (music.html)
The main menu hub containing responsive cards linking out to individual sub-genres.
```text
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to my collection</title>
    <style>
        body {
            margin: 0;
            text-align: center;
            padding-top: 50px;
            color: rgb(184, 21, 124);
            background: url('[https://i.ytimg.com/vi/e94hCLHEEsk/maxresdefault.jpg](https://i.ytimg.com/vi/e94hCLHEEsk/maxresdefault.jpg)') no-repeat center center fixed;
            background-size: cover;
        }
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
            z-index: -1;
        }
        .nav-container {
            margin-bottom: 30px;
        }
        .album-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 40px;
            max-width: 1200px;
            justify-content: center;
            margin: 0 auto;
            padding: 20px;
        }
        .album-card {
            width: 240px;
            background: rgba(255, 255, 255, .15);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, .2);
            border-radius: 18px;
            padding: 15px;
            text-decoration: none;
            color: white;
            transition: .4s ease;
            box-shadow: 0 10px 25px rgba(0, 0, 0, .25);
            margin: 0 auto;
        }
        .album-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-radius: 12px;
        }
        .album-info {
            margin-top: 18px;
        }
        .album-info h3 {
            margin: 0;
            font-size: 22px;
        }
        .album-info p {
            color: #dcdcdc;
            margin: 10px 0;
            line-height: 1.5;
        }
        .album-info span {
            font-size: 14px;
            color: #f5d5ff;
        }
        .album-card:hover {
            transform: translateY(-10px) rotate(-2deg);
            background: rgba(255, 255, 255, .22);
            box-shadow: 0 20px 40px rgba(0, 0, 0, .35);
        }
        .glass-btn {
            display: inline-block;
            padding: 12px 28px;
            margin: 5px;
            border-radius: 30px;
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgb(0, 0, 0);
            color: rgb(240, 197, 197);
            text-decoration: none;
            font-size: 16px;
            font-weight: 500;
            letter-spacing: 0.5px;
            cursor: pointer;
            transition: all 0.35s ease;
        }
        .glass-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 255, 255, 0.15);
        }
    </style>
</head>
<body>

    <div class="nav-container">
        <a href="index.html" class="glass-btn">🏡H♡me</a>
        <a href="comfort.html" class="glass-btn">❤️C♡mf♡rt S♡ngs</a>
        <a href="tpop.html" class="glass-btn">✨TP♡P S♡ng</a>
        <a href="ost.html" class="glass-btn">💿OST S♡ng</a>
        <a href="gmmtv.html" class="glass-btn">❤︎GMMTV S♡ng</a>
    </div>

    <h1 class="page-title"><b><i>💿Welcome to my collection.💿</i></b></h1>

    <div class="album-container">
        <!-- Comfort -->
        <a href="comfort.html" class="album-card">
            <img src="[https://i.pinimg.com/736x/d0/84/8a/d0848a18fc2ad7af76d47a2cd3d52d83.jpg](https://i.pinimg.com/736x/d0/84/8a/d0848a18fc2ad7af76d47a2cd3d52d83.jpg)" alt="Comfort Songs">
            <div class="album-info">
                <h3>❤️C♡mf♡rt S♡ngs</h3>
                <p>For the days I need a hug.</p>
                <span>4 Songs</span>
            </div>
        </a>

        <!-- T-Pop -->
        <a href="tpop.html" class="album-card">
            <img src="[https://i.pinimg.com/736x/86/69/c4/8669c461820b025f32cc3abbbe1c4134.jpg](https://i.pinimg.com/736x/86/69/c4/8669c461820b025f32cc3abbbe1c4134.jpg)" alt="Tpop Songs">
            <div class="album-info">
                <h3>🎤 T-Pop</h3>
                <p>Energetic beats and catchy choruses.</p>
                <span>4 Songs</span>
            </div>
        </a>

        <!-- OST -->
        <a href="ost.html" class="album-card">
            <img src="[https://i.pinimg.com/736x/6b/4f/52/6b4f52ef6c1d17da5da5dc928d96980f.jpg](https://i.pinimg.com/736x/6b/4f/52/6b4f52ef6c1d17da5da5dc928d96980f.jpg)" alt="OST Songs">
            <div class="album-info">
                <h3>🎬 Thai OSTs</h3>
                <p>The songs behind unforgettable scenes.</p>
                <span>4 Songs</span>
            </div>
        </a>

        <!-- GMMTV -->
        <a href="gmmtv.html" class="album-card">
            <img src="[https://i.pinimg.com/736x/78/9a/b9/789ab95e6c4d892f4855ad682a7f9af1.jpg](https://i.pinimg.com/736x/78/9a/b9/789ab95e6c4d892f4855ad682a7f9af1.jpg)" alt="GMMTV Songs">
            <div class="album-info">
                <h3>❤︎ GMMTV S♡ng</h3>
                <p>Melodies from your favorite series.</p>
                <span>4 Songs</span>
            </div>
        </a>
    </div>

<script>
    window.addEventListener("offline", () => {
        window.location.href = "404.html";
    });
</script>
</body>
</html>
```
🎵 Dynamic Category Code Blueprint
Every secondary collection page utilizes the exact same foundational layout engine. Below is the master configuration. Replace the data configuration details within const songs array to expand categories.

Standard Template (comfort.html)
```text
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>❤️C♡mf♡rt S♡ngs❤️</title>
    <style>
        body {
            margin: 0;
            text-align: center;
            padding-top: 50px;
            color: rgb(184, 21, 124);
            background: url('[https://i.ytimg.com/vi/e94hCLHEEsk/maxresdefault.jpg](https://i.ytimg.com/vi/e94hCLHEEsk/maxresdefault.jpg)') no-repeat center center fixed;
            background-size: cover;
        }
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.6);
            z-index: -1;
        }
        .nav-container { margin-bottom: 20px; }
        .song-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px 60px;
            padding: 50px;
            max-width: 1400px;
            margin: 0 auto;
            justify-items: center;
        }
        .music-card {
            width: 100%;
            max-width: 350px;
            padding: 30px 20px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 15px;
            border-radius: 35px;
            background: rgba(255, 255, 255, .08);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, .2);
            box-shadow: 0 15px 35px rgba(0, 0, 0, .4);
            opacity: 0;
            transform: translateY(80px);
            transition: opacity 0.7s, transform 0.7s, box-shadow 0.4s;
        }
        .music-card.show { opacity: 1; transform: translateY(0); }
        .music-card:hover { box-shadow: 0 20px 45px rgba(0, 0, 0, .6); }
        .music-info { width: 100%; text-align: center; }
        .music-info h1 { color: rgb(239, 187, 114); font-size: 30px; margin-bottom: 5px; }
        .music-info p { color: #ffffff; font-size: 18px; margin-bottom: 20px; }
        .music-info audio { width: 90%; }
        .glass-btn {
            display: inline-block; padding: 12px 28px; border-radius: 30px;
            background: rgba(255, 255, 255, 0.12); backdrop-filter: blur(15px);
            border: 1px solid rgb(0, 0, 0); color: rgb(240, 197, 197);
            text-decoration: none; font-size: 16px; margin: 5px; transition: all 0.35s ease;
        }
        .glass-btn:hover { background: rgba(255, 255, 255, 0.2); transform: translateY(-3px); }
        .disc {
            width: 150px; height: 150px; border-radius: 50%;
            background: radial-gradient(circle, #ffffff 0%, #000000 10%, rgb(164, 0, 0) 13%, black 70%);
            border: 6px solid #000000; display: flex; justify-content: center; align-items: center;
            font-size: 35px; box-shadow: 0 0 20px red; transition: all .4s ease;
        }
        .disc:hover { transform: scale(1.05); cursor: pointer; }
        .spin { animation: rotate 3s linear infinite, glow 1.5s ease-in-out infinite; }
        @keyframes rotate { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
        @keyframes glow { 0%, 100% { box-shadow: 0 0 20px red; } 50% { box-shadow: 0 0 20px red, 0 0 45px red, 0 0 70px rgba(255, 0, 0, .8); } }
        .polaroid { width: 200px; background: #ffffffc2; padding: 10px 10px 40px; position: relative; transform: rotate(-6deg); box-shadow: 0 10px 25px rgba(0, 0, 0, .45); transition: .4s; }
        .polaroid img { width: 100%; display: block; }
        .polaroid span { display: block; margin-top: 15px; font-size: 22px; font-family: cursive; color: #000; }
        .polaroid:hover { transform: rotate(-2deg) translateY(-12px) scale(1.05); }
        .tape { width: 80px; height: 25px; background: #9a4242; position: absolute; top: -12px; left: 50%; transform: translateX(-50%) rotate(3deg); opacity: 0.8; transition: .4s; }
        .polaroid:hover .tape { transform: translateX(-50%) rotate(-4deg); }
    </style>
</head>
<body>

    <div class="nav-container">
        <a href="index.html" class="glass-btn">🏡H♡me</a>
        <a href="comfort.html" class="glass-btn">❤️C♡mf♡rt S♡ngs</a>
        <a href="ost.html" class="glass-btn">🎬OST S♡ngs</a>
        <a href="gmmtv.html" class="glass-btn">📺GMMTV S♡ngs</a>
        <a href="tpop.html" class="glass-btn">✨TP♡P S♡ngs</a>
    </div>

    <!-- UPDATE HEADER HERE PER PAGE -->
    <h1 class="page-title"><b><i>❤️C♡mf♡rt S♡ngs</i></b></h1>
    
    <div class="song-container" id="song-container"></div>

    <script>
    // DATA CONFIGURATION MATRIX: UPDATE PER PAGE TARGET
    const songs = [
        {
            title: "Last Twilight",
            artist: "William Jakrapatr",
            audio: "comfort/(Last Twilight)- William Jakrapatr.mp3",
            image: "[https://i.mydramalist.com/pd8rpn_3f.jpg](https://i.mydramalist.com/pd8rpn_3f.jpg)"
        },
        {
            title: "Feel Fan",
            artist: "Net James",
            audio: "comfort/Feel_Fan_-_Ne_(getmp3.pro).mp3",
            image: "[https://tse1.mm.bing.net/th/id/OIP.xaz111UsfhLXcN3zI_wlsgHaEK?rs=1&pid=ImgDetMain&o=7&rm=3](https://tse1.mm.bing.net/th/id/OIP.xaz111UsfhLXcN3zI_wlsgHaEK?rs=1&pid=ImgDetMain&o=7&rm=3)"
        },
        {
            title: "Why Dont You",
            artist: "Jeff Satur",
            audio: "comfort/Jeff_Satur_-_Why_Dont_You_(getmp3.pro).mp3",
            image: "[https://tse1.mm.bing.net/th/id/OIP.ci-Bn5P_VkaY4uNI4jy-ygAAAA?rs=1&pid=ImgDetMain&o=7&rm=3](https://tse1.mm.bing.net/th/id/OIP.ci-Bn5P_VkaY4uNI4jy-ygAAAA?rs=1&pid=ImgDetMain&o=7&rm=3)"
        },
        {
            title: "Just Friends",
            artist: "Nanon Korapat",
            audio: "comfort/NANON_KORAPAT_-_Just_Friends__(getmp3.pro).mp3",
            image: "[https://tse2.mm.bing.net/th/id/OIP.Xc_48BGO6cXIKmQ3yg0IQAHaHa?rs=1&pid=ImgDetMain&o=7&rm=3](https://tse2.mm.bing.net/th/id/OIP.Xc_48BGO6cXIKmQ3yg0IQAHaHa?rs=1&pid=ImgDetMain&o=7&rm=3)"
        }
    ];

    const container = document.getElementById("song-container");
    songs.forEach(song => {
        container.innerHTML += `
            <div class="music-card">
                <div class="music-info">
                    <h1><i>${song.title}</i></h1>
                    <p><b>${song.artist}</b></p>
                    <audio controls>
                        <source src="${song.audio}" type="audio/mpeg">
                    </audio>
                </div>
                <div class="disc">💿</div>
                <div class="polaroid">
                    <div class="tape"></div>
                    <img src="${song.image}" alt="${song.title}">
                    <span>${song.artist}</span>
                </div>
            </div>
        `;
    });

    const cards = document.querySelectorAll(".music-card");
    cards.forEach(card => {
        const audio = card.querySelector("audio");
        const disc = card.querySelector(".disc");

        audio.addEventListener("play", () => {
            document.querySelectorAll("audio").forEach(a => { if (a !== audio) a.pause(); });
            document.querySelectorAll(".disc").forEach(d => d.classList.remove("spin"));
            disc.classList.add("spin");
        });
        audio.addEventListener("pause", () => disc.classList.remove("spin"));
        audio.addEventListener("ended", () => disc.classList.remove("spin"));
    });

    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add("show"); });
    }, { threshold: 0.2 });
    cards.forEach(card => observer.observe(card));

    const audios = document.querySelectorAll("audio");
    audios.forEach((audio, index) => {
        audio.addEventListener("ended", () => {
            document.querySelectorAll(".disc")[index].classList.remove("spin");
            let nextIndex = (index + 1) >= audios.length ? 0 : index + 1;
            audios[nextIndex].play();
        });
    });

    window.addEventListener("offline", () => { window.location.href = "404.html"; });
    </script>
</body>
</html>
```
📝 Custom Content Injection Arrays
To build out tpop.html, ost.html, and gmmtv.html, copy the template above, update the page title/header text, and substitute the const songs configuration array with the corresponding data sets below:

A. T-Pop Data Config (tpop.html)
```text
const songs = [
    {
        title: "Your Heart",
        artist: "PROXIE",
        audio: "tpop/your_heart_proxie.mp3",
        image: "[https://images.unsplash.com/photo-1514525253161-7a46d19cd819?w=500](https://images.unsplash.com/photo-1514525253161-7a46d19cd819?w=500)"
    },
    {
        title: "Fire Boy",
        artist: "PP Krit",
        audio: "tpop/fire_boy_ppkrit.mp3",
        image: "[https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?w=500](https://images.unsplash.com/photo-1498038432885-c6f3f1b912ee?w=500)"
    },
    {
        title: "Test Me",
        artist: "4EVE",
        audio: "tpop/test_me_4eve.mp3",
        image: "[https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?w=500](https://images.unsplash.com/photo-1511671782779-c97d3d27a1d4?w=500)"
    },
    {
        title: "Shark No Bite",
        artist: " therearn ",
        audio: "tpop/shark_no_bite.mp3",
        image: "[https://images.unsplash.com/photo-1501386761578-eac5c94b800a?w=500](https://images.unsplash.com/photo-1501386761578-eac5c94b800a?w=500)"
    }
];
```
B. Original Soundtracks Data Config (ost.html)
```text
const songs = [
    {
        title: "True Love",
        artist: "NuNew",
        audio: "ost/true_love_nunew.mp3",
        image: "[https://images.unsplash.com/photo-1487180142328-0c4e37023af5?w=500](https://images.unsplash.com/photo-1487180142328-0c4e37023af5?w=500)"
    },
    {
        title: "Kankat",
        artist: "Boy Sompob",
        audio: "ost/kankat_boysompob.mp3",
        image: "[https://images.unsplash.com/photo-1459749411175-04bf5292ceea?w=500](https://images.unsplash.com/photo-1459749411175-04bf5292ceea?w=500)"
    },
    {
        title: "A Tale of Thousand Stars",
        artist: "Gun Napat",
        audio: "ost/1000stars_gun.mp3",
        image: "[https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?w=500](https://images.unsplash.com/photo-1446776811953-b23d57bd21aa?w=500)"
    },
    {
        title: "Debt",
        artist: "Bright Vachirawit",
        audio: "ost/debt_bright.mp3",
        image: "[https://images.unsplash.com/photo-1518609878373-06d740f60d8b?w=500](https://images.unsplash.com/photo-1518609878373-06d740f60d8b?w=500)"
    }
];
```

So thats how you make personal Vinly webpage for your self
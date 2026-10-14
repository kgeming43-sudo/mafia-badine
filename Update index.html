<!DOCTYPE html>
<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مافیا بادینی - Mafia Badini</title>
    <style>
        :root {
            --bg-color: #121212;
            --panel-bg: #1e1e1e;
            --accent-color: #e50914;
            --text-color: #ffffff;
            --text-secondary: #b3b3b3;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        .container {
            width: 100%;
            max-width: 450px;
            background: var(--panel-bg);
            padding: 25px;
            border-radius: 12px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.6);
            text-align: center;
        }
        h1 {
            color: var(--accent-color);
            margin-bottom: 5px;
        }
        p.subtitle {
            color: var(--text-secondary);
            font-size: 14px;
            margin-bottom: 20px;
        }
        .btn {
            background-color: var(--accent-color);
            color: white;
            border: none;
            padding: 12px 20px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            margin-top: 10px;
            transition: 0.3s;
        }
        .btn:hover {
            opacity: 0.9;
        }
        input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            background: #2a2a2a;
            border: 1px solid #444;
            border-radius: 8px;
            color: white;
            font-size: 16px;
            box-sizing: border-box;
        }
        .hidden {
            display: none !important;
        }
        .card {
            background: #2a2a2a;
            padding: 20px;
            border-radius: 8px;
            margin: 15px 0;
            border: 2px solid var(--accent-color);
        }
        ul {
            list-style: none;
            padding: 0;
            text-align: right;
        }
        li {
            background: #2a2a2a;
            padding: 8px 12px;
            margin: 5px 0;
            border-radius: 6px;
        }
    }
    </style>
</head>
<body>

<div class="container" id="app">
    <h1>مافیا بادینی</h1>
    <p class="subtitle">سیستەمێ ئۆنلاین بۆ یارییا مافیا</p>

    <!-- بەشێ سەرەکی (چوونا ژوورێ یان دروستکرنێ) -->
    <div id="auth-screen">
        <input type="text" id="player-name" placeholder="ناڤێ خۆ لێرە بنڤیسە...">
        <button class="btn" onclick="createRoom()">دروستکرنا ژوورەکێ نوو</button>
        <hr style="border: 0.5px solid #333; margin: 20px 0;">
        <input type="text" id="room-code-input" placeholder="کۆدێ ژوورێ لێرە بنڤیسە...">
        <button class="btn" style="background-color: #333;" onclick="joinRoom()">چوونا ژوورێ</button>
    </div>

    <!-- بەشێ ژوورێ و لێستا یاریزانا -->
    <div id="room-screen" class="hidden">
        <h3 id="display-room-code" style="color: #4CAF50;"></h3>
        <p>هەڤالێن تە یێن د ژوورێ دا:</p>
        <ul id="players-list"></ul>
        <button class="btn hidden" id="start-game-btn" onclick="startGame()">دەستپێکرنا یاریێ و دابەشکرنا ڕۆلان</button>
    </div>

    <!-- بەشێ نیشاندانا ڕۆلێ نهێنی -->
    <div id="game-screen" class="hidden">
        <h2>ڕۆلێ تە یێ نهێنی</h2>
        <div class="card">
            <h1 id="my-role" style="font-size: 28px;">---</h1>
            <p id="my-role-desc">چاڤەڕێ بە...</p>
        </div>
    </div>
</div>

<script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-app.js";
    import { getDatabase, ref, set, get, update, onValue, push } from "https://www.gstatic.com/firebasejs/13.0.0/firebase-database.js";

    // ڕێکخستنێن Firebase یێن تە[span_1](start_span)[span_1](end_span)
    const firebaseConfig = {
        apiKey: "AIzaSyApi9n_0mZM1-ErqnBZTk[span_2](start_span)[span_2](end_span)...", // (ئەو کۆدێ تە گرتى لێرە تەمام بکە ئەگەر کێم هەبوو)
        authDomain: "mafia-badine.firebaseapp.com[span_3](start_span)"[span_3](end_span),
        databaseURL: "https://mafia-badine-default-rtdb.firebaseio.com[span_4](start_span)"[span_4](end_span),
        projectId: "mafia-badine[span_5](start_span)"[span_5](end_span),
        storageBucket: "mafia-badine.appspot.com",
        messagingSenderId: "...",
        appId: "..."
    };

    const app = initializeApp(firebaseConfig);
    const db = getDatabase(app);

    let currentRoom = null;
    let myName = null;
    let myId = 'user_' + Math.random().toString(36).substr(2, 9);

    window.createRoom = function() {
        myName = document.getElementById('player-name').value;
        if (!myName) {
            alert('تکایە ناڤێ خۆ بنڤیسە!');
            return;
        }
        currentRoom = Math.random().toString(36).substr(2, 6).toUpperCase();
        
        const roomRef = ref(db, 'rooms/' + currentRoom);
        set(roomRef, {
            host: myId,
            status: 'waiting',
            players: {
                [myId]: { name: myName, role: 'چاڤەڕێ' }
            }
        }).then(() => {
            enterRoomUI();
        });
    };

    window.joinRoom = function() {
        myName = document.getElementById('player-name').value;
        currentRoom = document.getElementById('room-code-input').value.toUpperCase();
        if (!myName || !currentRoom) {
            alert('تکایە ناڤ و کۆدێ ژوورێ بنڤیسە!');
            return;
        }

        const playerRef = ref(db, `rooms/${currentRoom}/players/${myId}`);
        get(ref(db, `rooms/${currentRoom}`)).then((snapshot) => {
            if (snapshot.exists()) {
                set(playerRef, { name: myName, role: 'چاڤەڕێ' }).then(() => {
                    enterRoomUI();
                });
            } else {
                alert('ڤەژوور یا هەی نەدیت!');
            }
        });
    };

    function enterRoomUI() {
        document.getElementById('auth-screen').classList.add('hidden');
        document.getElementById('room-screen').classList.remove('hidden');
        document.getElementById('display-room-code').innerText = "کۆدێ ژوورێ: " + currentRoom;

        const roomRef = ref(db, `rooms/${currentRoom}`);
        onValue(roomRef, (snapshot) => {
            const data = snapshot.val();
            if (!data) return;

            // نیشاندانا لیستا یاریزانا
            const list = document.getElementById('players-list');
            list.innerHTML = '';
            const players = data.players || {};
            
            let isHost = (data.host === myId);
            if (isHost && data.status === 'waiting') {
                document.getElementById('start-game-btn').classList.remove('hidden');
            }

            Object.keys(players).forEach(id => {
                let li = document.createElement('li');
                li.innerText = players[id].name + (id === data.host ? ' (سەرکردێ ژوورێ)' : '');
                list.appendChild(li);
            });

            // ئەگەر یاری دەستپێکر، ڕۆلا خۆ ببینە
            if (data.status === 'playing') {
                document.getElementById('room-screen').classList.add('hidden');
                document.getElementById('game-screen').classList.remove('hidden');
                
                let myRole = players[myId] ? players[myId].role : 'هاووڵاتی';
                document.getElementById('my-role').innerText = myRole;
                if(myRole.includes('مافیا')) {
                    document.getElementById('my-role-desc').innerText = 'تو مافیا یی! هەڤالێن خۆ ژناڤ ببە ب دزی.';
                } else {
                    document.getElementById('my-role-desc').innerText = 'تو هاووڵاتی یی! هەوڵ بدە مافیایان ئاشکرا بکەی.';
                }
            }
        });
    }

    window.startGame = function() {
        const roomRef = ref(db, `rooms/${currentRoom}`);
        get(roomRef).then((snapshot) => {
            const data = snapshot.val();
            const players = data.players;
            const playerIds = Object.keys(players);
            
            // دابەشکرنا ڕۆلان ب رێژەیەکا تەمام
            let roles = ['مافیا', 'دکتۆر', 'پۆلیس'];
            while(roles.length < playerIds.length) {
                roles.push('هاووڵاتی');
            }
            // Shuffle roles
            roles.sort(() => Math.random() - 0.5);

            let updates = {};
            updates[`rooms/${currentRoom}/status`] = 'playing';
            
            playerIds.forEach((id, index) => {
                updates[`rooms/${currentRoom}/players/${id}/role`] = roles[index];
            });

            update(ref(db), updates);
        });
    };
</script>

</body>
</html>

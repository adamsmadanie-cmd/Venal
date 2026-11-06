<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>VÉNAL — Informations c'est ici</title>

  <style>
    :root {
      --bg: #FAFAFA;
      --surface: #FFFFFF;
      --text: #0D0D0D;
      --muted: #666666;
      --border: #E5E5E5;
      --accent: #000000;
      --radius: 12px;
      --shadow-sm: 0 2px 6px rgba(0, 0, 0, 0.04);
      --shadow-md: 0 4px 16px rgba(0, 0, 0, 0.08);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.5;
      padding-bottom: 60px;
    }

    /* Navigation Haute Couture */
    header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(255, 255, 255, 0.92);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
      padding: 14px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .brand {
      display: flex;
      flex-direction: column;
    }

    .logo-3d {
      font-weight: 900;
      font-size: 1.5rem;
      letter-spacing: 2px;
      color: var(--accent);
      text-transform: uppercase;
      text-shadow: 1px 1px 0px rgba(0,0,0,0.12);
    }

    .slogan {
      font-size: 0.65rem;
      letter-spacing: 1.2px;
      color: var(--muted);
      text-transform: uppercase;
      font-weight: 700;
    }

    .nav-btns {
      display: flex;
      gap: 10px;
    }

    /* Boutons Éditoriaux Premium */
    .btn {
      background: var(--accent);
      color: #FFFFFF;
      border: 1px solid var(--accent);
      padding: 10px 18px;
      border-radius: var(--radius);
      font-size: 0.85rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1);
      box-shadow: var(--shadow-sm);
    }

    .btn:active {
      transform: scale(0.97);
    }

    .btn-outline {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
      box-shadow: none;
    }

    .btn-outline:hover {
      background: #F0F0F0;
    }

    /* Layout principal */
    main {
      max-width: 680px;
      margin: 0 auto;
      padding: 20px 16px;
    }

    /* Cadres animés 2D avec effet scanner */
    .card {
      background: var(--surface);
      border-radius: var(--radius);
      padding: 24px;
      margin-bottom: 20px;
      position: relative;
      border: 1px solid var(--border);
      box-shadow: var(--shadow-md);
      overflow: hidden;
    }

    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--accent), transparent);
      animation: scan 5s infinite linear;
    }

    @keyframes scan {
      0% { left: -100%; }
      50% { left: 100%; }
      100% { left: 100%; }
    }

    /* Formulaires et Entrées */
    .form-group {
      margin-bottom: 16px;
    }

    label {
      display: block;
      font-size: 0.75rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      margin-bottom: 6px;
      color: var(--muted);
    }

    input, textarea {
      width: 100%;
      padding: 14px;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      font-size: 0.95rem;
      background: #FAFAFA;
      color: var(--text);
      outline: none;
      transition: all 0.2s ease;
    }

    input:focus, textarea:focus {
      border-color: var(--accent);
      background: #FFFFFF;
      box-shadow: 0 0 0 2px rgba(0,0,0,0.05);
    }

    /* Profil et Fil de presse */
    .post-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 14px;
    }

    .avatar {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: #EEEEEE;
      object-fit: cover;
      border: 1px solid var(--border);
    }

    .post-author {
      font-weight: 700;
      font-size: 0.95rem;
    }

    .badge-press {
      display: inline-block;
      font-size: 0.65rem;
      background: #000000;
      color: #FFFFFF;
      padding: 3px 8px;
      border-radius: 4px;
      text-transform: uppercase;
      font-weight: 700;
      margin-left: 6px;
    }

    .post-title {
      font-size: 1.25rem;
      font-weight: 800;
      line-height: 1.3;
      margin-bottom: 10px;
    }

    .post-img {
      width: 100%;
      max-height: 360px;
      object-fit: cover;
      border-radius: var(--radius);
      margin: 12px 0;
      border: 1px solid var(--border);
    }

    .post-content {
      font-size: 0.98rem;
      color: #222222;
      white-space: pre-line;
      line-height: 1.6;
    }

    .hidden {
      display: none !important;
    }
  </style>
</head>
<body>

  <header>
    <div class="brand">
      <span class="logo-3d">VÉNAL</span>
      <span class="slogan">Informations c'est ici</span>
    </div>
    <div class="nav-btns">
      <button class="btn btn-outline" id="btn-profile" onclick="toggleSection('profile-sec')">Profil</button>
      <button class="btn" id="btn-auth" onclick="toggleAuthModal()">Connexion</button>
    </div>
  </header>

  <main>
    <!-- Espace d'Authentification -->
    <div class="card hidden" id="auth-sec">
      <h3 style="margin-bottom: 14px; font-weight: 800;">Espace Journaliste & Membre</h3>
      <div class="form-group">
        <label>Email professionnel</label>
        <input type="email" id="auth-email" placeholder="journaliste@venal.com">
      </div>
      <div class="form-group">
        <label>Mot de passe</label>
        <input type="password" id="auth-pass" placeholder="••••••••">
      </div>
      <div style="display: flex; gap: 10px;">
        <button class="btn" style="flex: 1;" onclick="handleLogin()">Se connecter</button>
        <button class="btn btn-outline" style="flex: 1;" onclick="handleRegister()">S'inscrire</button>
      </div>
    </div>

    <!-- Section Édition de Profil -->
    <div class="card hidden" id="profile-sec">
      <h3 style="margin-bottom: 14px; font-weight: 800;">Éditer le Profil Professionnel</h3>
      <div class="form-group">
        <label>Nom complet / Pseudonyme</label>
        <input type="text" id="prof-name" placeholder="Ex: Adams">
      </div>
      <div class="form-group">
        <label>Organisme de Presse / Média</label>
        <input type="text" id="prof-media" placeholder="Ex: VÉNAL Press">
      </div>
      <div class="form-group">
        <label>Numéro de Carte de Presse</label>
        <input type="text" id="prof-card" placeholder="Ex: CI-2026-99X">
      </div>
      <div class="form-group">
        <label>URL Photo de Profil</label>
        <input type="url" id="prof-photo" placeholder="https://...">
      </div>
      <div class="form-group">
        <label>Bio & Domaine d'expertise</label>
        <textarea id="prof-bio" rows="3" placeholder="Journaliste d'investigation politique..."></textarea>
      </div>
      <button class="btn" style="width: 100%;" onclick="saveProfile()">Mettre à jour le profil</button>
    </div>

    <!-- Espace de Publication d'Information -->
    <div class="card" id="post-create-sec">
      <h3 style="margin-bottom: 14px; font-weight: 800;">Publier une Information</h3>
      <div class="form-group">
        <input type="text" id="post-title" placeholder="Titre principal de l'article...">
      </div>
      <div class="form-group">
        <input type="url" id="post-img" placeholder="URL de l'image de couverture (optionnel)">
      </div>
      <div class="form-group">
        <textarea id="post-body" rows="4" placeholder="Rédigez votre rapport ou dépêche d'information..."></textarea>
      </div>
      <button class="btn" style="width: 100%;" onclick="publishPost()">Diffuser l'article</button>
    </div>

    <!-- Fil d'Actualités dynamique -->
    <div id="feed-container">
      <!-- Les dépêches sont synchronisées ici en temps réel -->
    </div>
  </main>

  <!-- Script Firebase Modulaire v13 -->
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/13.2.0/firebase-app.js";
    import { getAnalytics } from "https://www.gstatic.com/firebasejs/13.2.0/firebase-analytics.js";
    import { 
      getAuth, 
      createUserWithEmailAndPassword, 
      signInWithEmailAndPassword, 
      signOut, 
      onAuthStateChanged 
    } from "https://www.gstatic.com/firebasejs/13.2.0/firebase-auth.js";
    import { 
      getFirestore, 
      doc, 
      getDoc, 
      setDoc, 
      collection, 
      addDoc, 
      query, 
      orderBy, 
      onSnapshot, 
      serverTimestamp 
    } from "https://www.gstatic.com/firebasejs/13.2.0/firebase-firestore.js";

    // Clés de configuration officielles Firebase
    const firebaseConfig = {
      apiKey: "AIzaSyDwIDLu3SLGlSKKzQoCS6euaayhyFuoNK0",
      authDomain: "venal-app-d34d4.firebaseapp.com",
      projectId: "venal-app-d34d4",
      storageBucket: "venal-app-d34d4.firebasestorage.app",
      messagingSenderId: "885175897840",
      appId: "1:885175897840:web:f409cbf7d18d0184f23c35",
      measurementId: "G-EL589DZYGY"
    };

    const app = initializeApp(firebaseConfig);
    const analytics = getAnalytics(app);
    const auth = getAuth(app);
    const db = getFirestore(app);

    let currentUser = null;

    // Fonctions globales exposées au DOM
    window.toggleSection = function(id) {
      document.getElementById(id).classList.toggle('hidden');
    }

    window.toggleAuthModal = function() {
      if (currentUser) {
        signOut(auth).then(() => alert("Déconnexion effectuée."));
      } else {
        document.getElementById('auth-sec').classList.toggle('hidden');
      }
    }

    window.handleRegister = async function() {
      const email = document.getElementById('auth-email').value;
      const pass = document.getElementById('auth-pass').value;
      if(!email || !pass) return alert("Veuillez remplir l'email et le mot de passe.");
      try {
        const res = await createUserWithEmailAndPassword(auth, email, pass);
        await setDoc(doc(db, 'users', res.user.uid), {
          name: email.split('@')[0],
          media: 'Indépendant',
          card: 'En attente',
          photo: '',
          bio: ''
        });
        document.getElementById('auth-sec').classList.add('hidden');
        alert("Compte créé avec succès !");
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    window.handleLogin = async function() {
      const email = document.getElementById('auth-email').value;
      const pass = document.getElementById('auth-pass').value;
      if(!email || !pass) return alert("Veuillez saisir votre email et mot de passe.");
      try {
        await signInWithEmailAndPassword(auth, email, pass);
        document.getElementById('auth-sec').classList.add('hidden');
      } catch (e) {
        alert("Erreur de connexion: " + e.message);
      }
    }

    window.saveProfile = async function() {
      if (!currentUser) return alert("Veuillez d'abord vous connecter.");
      try {
        await setDoc(doc(db, 'users', currentUser.uid), {
          name: document.getElementById('prof-name').value,
          media: document.getElementById('prof-media').value,
          card: document.getElementById('prof-card').value,
          photo: document.getElementById('prof-photo').value,
          bio: document.getElementById('prof-bio').value
        }, { merge: true });
        alert("Profil professionnel mis à jour !");
        document.getElementById('profile-sec').classList.add('hidden');
      } catch (e) {
        alert("Erreur: " + e.message);
      }
    }

    window.publishPost = async function() {
      if (!currentUser) return alert("Connexion requise pour publier.");
      const title = document.getElementById('post-title').value;
      const img = document.getElementById('post-img').value;
      const body = document.getElementById('post-body').value;

      if (!title || !body) return alert("Veuillez saisir au moins le titre et le texte de l'article.");

      try {
        const userDocRef = doc(db, 'users', currentUser.uid);
        const userSnap = await getDoc(userDocRef);
        const userData = userSnap.exists() ? userSnap.data() : {};

        await addDoc(collection(db, 'posts'), {
          title,
          img,
          body,
          author: userData.name || 'Journaliste',
          media: userData.media || 'Presse',
          photo: userData.photo || 'https://via.placeholder.com/44',
          createdAt: serverTimestamp()
        });

        document.getElementById('post-title').value = '';
        document.getElementById('post-img').value = '';
        document.getElementById('post-body').value = '';
        alert("Article mis en ligne !");
      } catch (e) {
        alert("Erreur d'envoi: " + e.message);
      }
    }

    // Écouteur de statut d'authentification
    onAuthStateChanged(auth, async (user) => {
      currentUser = user;
      const authBtn = document.getElementById('btn-auth');
      if (user) {
        authBtn.innerText = "Déconnexion";
        const userDoc = await getDoc(doc(db, 'users', user.uid));
        if (userDoc.exists()) {
          const data = userDoc.data();
          document.getElementById('prof-name').value = data.name || '';
          document.getElementById('prof-media').value = data.media || '';
          document.getElementById('prof-card').value = data.card || '';
          document.getElementById('prof-photo').value = data.photo || '';
          document.getElementById('prof-bio').value = data.bio || '';
        }
      } else {
        authBtn.innerText = "Connexion";
      }
    });

    // Écouteur en temps réel du fil de presse
    const q = query(collection(db, 'posts'), orderBy('createdAt', 'desc'));
    onSnapshot(q, (snapshot) => {
      const feed = document.getElementById('feed-container');
      feed.innerHTML = '';
      snapshot.forEach((documentSnap) => {
        const data = documentSnap.data();
        feed.innerHTML += `
          <div class="card">
            <div class="post-header">
              <img src="${data.photo || 'https://via.placeholder.com/44'}" class="avatar" alt="Avatar">
              <div>
                <div class="post-author">${data.author} <span class="badge-press">${data.media}</span></div>
              </div>
            </div>
            <div class="post-title">${data.title}</div>
            ${data.img ? `<img src="${data.img}" class="post-img" alt="Illustration">` : ''}
            <div class="post-content">${data.body}</div>
          </div>
        `;
      });
    });
  </script>
</body>
</html>

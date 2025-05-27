# BabyBinance-tap-
// app.js

let clickCount = 0;
let earned = 0;

document.getElementById("tapButton").addEventListener("click", () => {
  clickCount++;
  earned += 1; // 1 BABYBNB simulé par clic
  document.getElementById("clickCount").textContent = clickCount;
  document.getElementById("earned").textContent = earned;
});

document.getElementById("connectButton").addEventListener("click", async () => {
  if (typeof window.ethereum !== 'undefined') {
    try {
      const accounts = await window.ethereum.request({ method: 'eth_requestAccounts' });
      document.getElementById("walletAddress").textContent = `Wallet connecté: ${accounts[0]}`;
    } catch (error) {
      alert("Connexion refusée");
    }
  } else {
    alert("MetaMask non détecté !");
  }
});

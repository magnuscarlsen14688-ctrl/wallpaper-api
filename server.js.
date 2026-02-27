import express from "express";
import fetch from "node-fetch";
import cors from "cors";

const app = express();
app.use(cors());

const ACCESS_KEY = process.env.UNSPLASH_KEY;

app.get("/wallpapers", async (req, res) => {
  const query = req.query.q || "mobile wallpaper";
  const page = req.query.page || 1;

  try {
    const response = await fetch(
      `https://api.unsplash.com/search/photos?query=${query}&per_page=12&page=${page}&orientation=portrait&client_id=${ACCESS_KEY}`
    );
    const data = await response.json();
    res.json(data);
  } catch (error) {
    res.status(500).json({ error: "Error fetching images" });
  }
});

app.listen(3000, () => {
  console.log("Server running");
});

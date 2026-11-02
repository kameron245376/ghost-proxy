const express = require("express");
const app = express();

app.use(express.static("public"));

app.get("/api/check", async (req, res) => {
    const url = req.query.url;

    if (!url) {
        return res.status(400).json({ error: "Missing URL" });
    }

    try {
        const parsed = new URL(url);

        if (parsed.protocol !== "https:") {
            return res.status(400).json({ error: "HTTPS required" });
        }

        const allowed = [
            "example.com",
            "www.example.com"
        ];

        if (!allowed.includes(parsed.hostname)) {
            return res.status(403).json({
                error: "Website not approved"
            });
        }

        const response = await fetch(parsed.href, {
            redirect: "error",
            signal: AbortSignal.timeout(8000)
        });

        res.json({
            accessible: response.ok,
            status: response.status,
            url: parsed.href
        });

    } catch (error) {
        res.status(400).json({
            error: "Could not access website"
        });
    }
});

const PORT = process.env.PORT || 3000;

app.listen(PORT, () => {
    console.log("Ghost Proxy running on port " + PORT);
});

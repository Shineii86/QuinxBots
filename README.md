# My BB

This is a small web application that uses the bots.business `AppAPI` to manage and edit bot commands. It was created mainly to scratch an itch: a nicer UI for command search, alias lookups, and a friendly code editor with real find & replace. Nothing fancy — pragmatic, fast, and easy to fork.

Why this exists: I like good tooling and bots.business doesn't pay me to build this, so I add features when I have free time. If you want more features, help out.

> **Important**: You need an **API key** to access your bot through this web app. We do not save anything to our server. The API key you enter is only saved to your **local storage**. If you see a similar web app on any domain other than `bb.tgbro.link`, do not open it — it could be a phishing page trying to steal your API key.

---

## Key features

* Connects to **bots.business API** using your API key directly from the frontend.
* Modern responsive UI built with **Bootstrap** (components, grid, modals).
* Command search supporting aliases (fast lookup by alias or name).
* New code editor with:

  * Search and **Find & Replace** (exact / case-sensitive options).
  * Syntax highlighting powered by **CodeMirror**.
* Minimal authentication flow (uses the API key you supply).
* Simple admin pages: view commands, edit command metadata, push edits.

---

## Notable design decisions (read: why things are rough around edges)

* This is intentionally small; not trying to be some giant framework or paid product.
* UX favors directness over over-engineered abstractions.
* Security: treat the API key like a password. The repo contains no secrets — you must provide your own.
* We directly send requests to the bots.business API from the **frontend**. There is **no backend**, so there’s no way we can see your API key.
* I add new features when I have time. If you need something done urgently, PRs welcome.

---

## How it talks to bots.business

The app expects you to provide an **API key** (stored in local storage). All requests are sent directly from the browser to the bots.business API.

A typical flow:

* Frontend requests to bb api.
* The request includes `api_key=<YOUR_API_KEY>`.
* Response is rendered directly in the UI.

---

## Editor features (the stuff I actually care about)

* **Search commands using alias**: type an alias or command name in the search box — results include commands and their aliases so you can find the right item fast.
* **Find & Replace**: editor toolbar → search → replace. Replace supports exact match and case-sensitive toggle. Use responsibly — no undo history for batch replaces (so don't be sloppy).
* **CodeMirror syntax highlighting**: makes editing commands less painful.

Developer note: the editor is intentionally lightweight. If you want VSCode-like features, contribute a PR (I won't be offended).

---

## Contributing

Contributors are welcome. Keep these rules in mind:

* Open an issue before doing heavy work so we don't duplicate.
* Keep PRs focused and small. One concern per PR.
* Add tests if you add logic (even small). If you can't add tests, explain why in the PR.
* Respect the code style used in repository — there are no religious formatting bikesheds here.


---


## Credits

* Me for nothing

---

## Final note (because I'm direct)

This was built by one dev in spare hours. It works, but it's not perfect. If you like it — fork it. If you don't — fix it and send a PR. If you need features, offer to sponsor development or help code them. I won't pretend this is a commercial product; it's a useful, honest tool.

Happy hacking — and read the code before hitting replace on production.

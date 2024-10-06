# Publish to Ghost
It allows you to send Obsidian notes to the [Ghost](https://ghost.org) publishing platform, either as published or draft posts or pages.

## Usage

### Authentication
Send to Ghost can use either a **Staff Access Token** or an **[Admin API Key](https://ghost.org/integrations/custom-integrations/)**. Each staff member has their own Staff Access Token which gives Send to Ghost permission to do all the things that they can do, while an Admin API Key must be created manually and gives all permissions. Because Obsidian plugins [can't store sensitive information securely](https://forum.obsidian.md/t/a-place-for-plugins-sensitive-data/18308), you should use a Staff Access Token, since its access is more limited. You could also consider creating a seperate staff user with barebones permissions for uploading posts if you are concerned about the security of your site.

Note that the Staff Access Tokens of users who have Administrator or Owner permissions have the same access as Admin API Keys. They are still preferred, since their access to your site is tied to the access of the staff member who they belong to. They are also usable with Starter sites on Ghost Pro.

#### Finding your Access Token
To get your Staff Access Token, go to the admin dashboard and click the avatar in the bottom-right corner, then click "Your Profile". Scroll down to find the token, hover over it and click the "copy" button to copy it to the clipboard.

### Using the plugin
After installing the plugin in Obsidian, go to its settings and fill in the fields. Put the URL of your Ghost site in the "Site URL" field (or the `ghost.io` URL if you're using Ghost Pro), and your Staff Access Token/Admin API Key in the "Access Token" field. You can now click the ghost icon in the ribbon menu on the left or use the "Send to Ghost" command in the command palette to send the currently open note to Ghost.

### Front Matter format

Send to Ghost uses front matter to set Ghost-specific settings such as the title, tags, and the featured image. You can add front matter by enclosing it in `---` at the beginning of a note.

The following options are supported:

```md
---
title: String (default: filename)
tags: (default: none)
- tag1
- tag2
featured: Boolean (default: false)
published: Boolean (default: false)
excerpt: String (default: blank)
feature_image: String (default: blank)
---
```

## Development

This plugin uses PNPM for dependency management.

-   Clone the repository.
-   Run `pnpm i` to install the necessary dependencies
-   Run `pnpm dev` to automaticlly recompile as the project files change.

## Manual installation

-   Run `pnpm build`
-   Copy `main.js` and `manifest.json` to `VaultFolder/.obsidian/plugins/send-to-ghost/` where `Vaultfolder` is the location of your Obsidian vault.

## Change log
2024-10-06: I created this fork for my Publish to Ghost plugin to help publish my Obsidian notes on a Ghost website as posts and pages. The previous plugins only allowed you to create blog posts from Obsidian notes, and not pages. 

This was forked [Obsidian Send to Ghost](https://github.com/Southpaw1496/obsidian-send-to-ghost) by [Southpaw1496](https://southpaw1496.me), which is still being maintained.

That was forked from an earlier [obsidian-ghost-publish](https://github.com/jaynguyens/obsidian-ghost-publish) plugin by Jay Nguyen that is no longer available.

## Issues & Support
If you find a bug, please submit an [issue](https://github.com/warrenweb/publish-to-ghost). Otherwise, please contact me via [WarrenWeb](https://blog.warrenweb.net/contact).

For the earlier fork, Obsidian Send to Ghost, submit any bugs at [issue](https://github.com/Southpaw1496/obsidian-send-to-ghost), and please contact him via [my website](https://southpaw1496.me).

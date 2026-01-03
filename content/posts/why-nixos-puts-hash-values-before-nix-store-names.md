---
date: "2025-01-26T12:41:06+00:00"
title: "Why NixOS Puts Hash Values Before Nix Store Names"
---

NixOS places hash values before Nix store names to maintain consistency and readability. Because hash values have a **fixed length** while store names can vary, this ordering ensures **uniform alignment** across paths. As a result, directory listings are easier to scan and navigate efficiently.

## Documentation

- <https://nixos.wiki/wiki/Valid_Nix_store_path_names>

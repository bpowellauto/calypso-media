# calypso-media

Public image host for [@calypsofuel](https://www.threads.com/@calypsofuel).

Instagram's API fetches images over the public internet — it can't accept an
upload from a laptop — so posted images need a stable public URL. That's all
this repo is.

## Everything here is public and permanent

Git keeps history, so deleting a file later does not really remove it. Nothing
should land here that shouldn't be public forever.

## Metadata is stripped before anything is committed

Photos are processed by `src/media.py` in the boat-fuel-social project, which
strips **all** EXIF — including GPS coordinates — and downscales before writing
into `images/`. That check fails closed: if metadata survives, the file is
deleted rather than published.

This matters because phone photos of fuel deliveries would otherwise carry the
exact slip location of a customer's boat.

## Layout

```
images/    what gets served
```

URLs look like:

```
https://raw.githubusercontent.com/bpowellauto/calypso-media/main/images/<file>.jpg
```

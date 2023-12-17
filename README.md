# Couch-Tracker

An Android application, to keep track of the TV shows you follow, and the movies you've watched.

This repository contains all the documents and design decisions we've made.


## Tenets

- Open-source
- no ads, no trackers and no third party integrations which are not strictly necessary to make the app work
- no paywalling for features done locally and don't require an ongoing cost from us
- Low (or zero) licensing/hosting fees, low architectural complexity
- User data is owned by each user, and is always available to them. This data is in an open format
- Focused on user data: discover/explore sections and the likes may have a place, but it is not central
- Fast and simple


## General overview

The app stores the user data in a file, logically owned by the user. The file may be either in the app's or user's partition, to provide respectively a managed or unmanaged experience. The user can switch between the two.

If the file is in the user's partition (unmanaged), the app will assume the file can be read and modified by other processes (e.g. Syncthing to sync it between multiple devices).

All the shows/movies/episodes/collections/actors referenced by the user data file will be downloaded and kept in sync automatically, this time in a local database owned by the app.

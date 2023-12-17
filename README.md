# Couch-Tracker

An Android application, to keep track of the TV shows you follow, and the movies you've watched.

This repository contains all the documents and design decisions we've made.


## Tenets

- Open-source
- No ads, no trackers
- For everything the app does locally, completely free
- Low (or zero) licensing/hosting fees, low architectural complexity
- User data is owned by each user, and is always available to them. This data is in an open format
- Fast and simple


## General overview

The app stores the user data in a file, logically owned by the user. The file will be in the user partition, and could be synced with other devices (e.g. using Synthing), backed up in the cloud, or read/written by other apps that understand the same file format.

All the shows/movies/episodes/collections/actors referenced by the last open user data file will be downloaded and kept in sync automatically, this time in a local database owned by the app.
This local data will be kept for a brief period of time after it is detected as unused, so switching between different user data files won't cause a complete re-download of everything.

Notifications, widgets, and all other aspects of the app that don't require active interactions will reference the last open user data file.

# Spotify Simulator

A Java project simulating a simplified Spotify‑like application. Users can follow each other, create playlists, play music, and upgrade to premium. The design uses the **Strategy pattern** to manage different user capabilities (regular vs. premium) and custom exceptions for error handling.

## Core Components

- `User` – stores username, password, followers/following lists, and a `UserBehavior` reference. Delegates `createPlaylist()`, `playMusic()`, and `buyPremium()` to the current behavior.
- `UserBehavior` – interface defining the three delegated actions.
- `RegularBehavior` – allows a maximum of 5 music plays, cannot create playlists, and can upgrade to premium by swapping behavior.
- `PremiumBehavior` – unlimited plays, can create playlists, and extends premium subscription duration.
- `Music` – track with title, singer, and play count. Provides search methods (`search()` by title or title+singer).
- `Playlist` – a collection of `Music` owned by a user. Requires password verification for editing, adding, or removing tracks.
- `InvalidOperationException` – custom unchecked exception for invalid inputs, permission errors, or capacity limits.

## What the project practices

Encapsulation, polymorphism, the **Strategy pattern** for dynamic behavior changes, runtime behavior swapping, and robust validation via custom exceptions. The model allows seamless transitions between regular and premium user states without modifying the `User` class.

# GDevelop and Playgama Bridge Integration Example

This repository provides a comprehensive example of how to integrate the **Playgama Bridge SDK** into a **GDevelop** project. It serves as a practical guide for game developers looking to publish their HTML5 games across a wide range of platforms and monetize them effectively.

## What is Playgama Bridge?

**Playgama Bridge** is a unified Software Development Kit (SDK) that allows HTML5 game developers to integrate their games with multiple distribution platforms using a single, streamlined process. By integrating Playgama Bridge, developers can reach a massive audience of over 300 million monthly active users across various platforms without the need to manage multiple SDKs and APIs.

### Key Benefits of Playgama Bridge:

- **One SDK, Many Platforms:** Integrate once and publish your game on numerous platforms, including CrazyGames, YouTube, Huawei, Telegram, and many more.
- **Monetization Made Easy:** Seamlessly implement interstitial and rewarded video ads to generate revenue from your games.
- **Cloud Saves:** Provide a better player experience with cross-device saving, allowing users to continue their progress on any device.
- **Simplified Development:** The SDK abstracts away the complexities of platform-specific APIs, allowing you to focus on creating great games.

## About This Example

This repository contains a simple GDevelop game that demonstrates the core functionalities of the Playgama Bridge SDK. The game consists of a player character, collectible coins, and a simple level progression system. It is designed to showcase the following key integration points:

- **SDK Initialization:** How to properly initialize the Playgama Bridge SDK and wait for it to be ready.
- **Ad Monetization:** How to display interstitial and rewarded ads at appropriate moments in the game.
- **Cloud Data Storage:** How to save and retrieve player data, such as the highest level unlocked.

## Getting Started

Follow these steps to get the project running on your local machine for development and testing purposes.

### Prerequisites

Before you begin, ensure you have the following installed:

- **GDevelop 5:** You can download the latest version for your operating system from the [official GDevelop website](https://gdevelop.io/).
- **Git:** (Optional, for cloning) You can download Git from [git-scm.com](https://git-scm.com/).

### Installation

1.  **Clone the repository:**
    Open your terminal or command prompt and run the following command to clone the repository to your local machine:
    ```bash
    git clone https://github.com/Playgama/bridge-gdevelop-example.git
    ```
    Alternatively, you can download the project as a ZIP file by clicking the "Code" button on the GitHub repository page and selecting "Download ZIP".

2.  **Open the project in GDevelop:**
    - Launch the GDevelop 5 application.
    - On the startup screen, select **"Open a project"**.
    - Navigate to the directory where you cloned or unzipped the repository (e.g., `bridge-gdevelop-example`).
    - Select the `PlaygamaBridgeExample.json` file and click **"Open"**.

3.  **Run the game:**
    - Once the project is open, you can run the game directly in the GDevelop editor by clicking the **"Preview"** button (play icon) in the top toolbar. This will launch a preview of the game in a new window.

4.  **Explore the implementation:**
    - Navigate through the different scenes (`Loader`, `LevelSelect`, `Game`) and open the event sheets to see how the Playgama Bridge integration is implemented.

## How It Works

The integration with Playgama Bridge is primarily handled through the GDevelop event system. Here's a breakdown of the key events:

- **`Loader` Scene:** This is the first scene that runs. Its purpose is to initialize the SDK and load any saved data before the game starts.
    - At the beginning of the scene, the `Initialize Playgama Bridge` action is called.
    - The game then waits for the `Playgama Bridge is ready` condition to be true.
    - Once the bridge is ready, the game retrieves the player's saved data from the cloud.
    - Finally, the `GAME_READY` message is sent to the SDK, and the game transitions to the `LevelSelect` scene.

- **`LevelSelect` Scene:** This scene allows the player to choose a level.
    - When the player chooses a level, an interstitial ad is shown before transitioning to the `Game` scene.

- **`Game` Scene:** This is where the main gameplay happens.
    - When the player completes a level, their progress is saved to the cloud using the `Save data` action.
    - When the player completes the fourth level, a rewarded ad is shown to simulate giving the player an in-game reward.

## Useful Links

- **[Playgama for Developers](https://playgama.com/developers)**
- **[Playgama Bridge Documentation](https://wiki.playgama.com/playgama/sdk/getting-started)**
- **[GDevelop Website](https://gdevelop.io/)**
- **[GDevelop Documentation](https://wiki.gdevelop.io/)**

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

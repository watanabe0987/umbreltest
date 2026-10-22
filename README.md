## Apps in this store

- `watanabe-donetick`, `watanabe-frigate`, `watanabe-hello-world`, `watanabe-mosquitto`, `watanabe-reostream`
- `watanabe-venice-tts` — Venice TTS Bridge

## Venice TTS Bridge (watanabe-venice-tts)

Wyoming protocol TTS proxy for Home Assistant backed by the Venice.ai speech API
(`tts-xai-v1`, xAI voices). Built on [roryeckel/wyoming_openai](https://github.com/roryeckel/wyoming_openai) v0.8.0.

**First start stops on purpose** until the API key exists:

```bash
sudo sh -c 'printf "TTS_OPENAI_KEY=YOUR_VENICE_API_KEY\n" > /home/umbrel/umbrel/app-data/watanabe-venice-tts/tts.env && chmod 600 /home/umbrel/umbrel/app-data/watanabe-venice-tts/tts.env'
```

Then restart the app. The file lives in the app data directory, so the key
survives app updates and reinstalls.

**Home Assistant:** Settings → Devices & Services → Add Integration → **Wyoming**,
host `192.168.0.56`, port `10300`. Announce with `tts.speak` targeting the new
TTS entity and a Sonos media player.

Voices: `eve ara rex sal leo helios luna iris sirius` (xAI voices via Venice).

## Umbrel Community App Store Template

This repository is a template to create an Umbrel Community App Store. These additional app stores allow developers to distribute applications without submitting to the [Official Umbrel App Store](https://github.com/getumbrel/umbrel-apps).

## How to use:

1. Start by clicking the "Use this template" button located above.
2. Assign an ID and name to your app store within the `umbrel-app-store.yml` file. This file specifies two important attributes:
    - `id` - Acts as a unique prefix for every app within your Community App Store. You must start your application's ID with your app store's ID. For instance, in this template, the app store ID is `sparkles`, and there's an app named `hello world`. Consequently, the app's ID should be: `sparkles-hello-world`.
    - `name` - This is the name of the Community App Store displayed in the umbrelOS UI.
3. Change the name of the `sparkles-hello-world` folder to match your app's ID. The app ID is for you to decide. For example, if your app store ID is `whistles`, and your app is named My Video Downloader, you could set its app ID to `whistles-my-video-downloader`, and rename the folder accordingly.
4. Next, enter your app's listing details in the `whistles-my-video-downloader/umbrel-app.yml`. These are displayed in the umbrelOS UI.
5. Include the necessary Docker services in `whistles-my-video-downloader/docker-compose.yml`.
6. That's it! Your Community App Store, featuring your unique app, is now set up and ready to go. To use your Community App Store, you can add its GitHub url the umbrelOS user interface as shown in the following demo:


https://user-images.githubusercontent.com/10330103/197889452-e5cd7e96-3233-4a09-b475-94b754adc7a3.mp4

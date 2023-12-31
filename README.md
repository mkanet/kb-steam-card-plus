
<div align="center">
  <h4 style="font-size: 1.5em;">A Home Assistant card for Steam and Roblox integrations</h4>
</div>
<br>

## Enhanced with <a href="https://github.com/jdeath/Roblox-Homeassistant/" style="text-decoration: none;">Roblox Custom Integration</a> support!
![New Screenshot](/images/Screenshot1.png)


## More Screenshots


### away \ offline state

![away \ offline state](https://thatkookooguy.github.io/https-assets/screenshots/kb-steam-card-offline.jpeg)

### online state

![online state](https://thatkookooguy.github.io/https-assets/screenshots/kb-steam-card-online.jpeg)

### while playing a game

![now playing](https://thatkookooguy.github.io/https-assets/screenshots/kb-steam-card-now-playing.jpeg)

## Installation

### Prerequisites
You need at least one [steam integration](https://www.home-assistant.io/integrations/steam_online/) to use with this card.

### HACS (recommended)

1. Go to the Community Store.
2. Search for `steam card`.
3. Press `Install`.

### Manual Installation

```yaml
resources:
  url: '<url-to-card.js>'
  type: module
```

## Usage

for a single user card, use `entity`:

```yaml
entity: sensor.steam_<steam-id>
type: 'custom:kb-steam-card'
```

you can change the username using the following:

```yaml
entity: sensor.steam_<steam-id>
friendly_name: Myself
type: 'custom:kb-steam-card'
```

for multiple users, use the `entities` attribute:
![](screenshots/multi.png)

```yaml
entities:
  - sensor.steam_<steam-id>
  - sensor.steam_<steam-id>
  - sensor.steam_<steam-id>
type: 'custom:kb-steam-card'
```

you can also use a prefix selector to select all steam sensors:

```yaml
type: 'custom:kb-steam-card'
entities: sensor.steam_
```

to show only **online users**, add the `online_only` attribute:

```yaml
type: 'custom:kb-steam-card'
entities: sensor.steam_
online_only: true
```

you can also show the game header image as background with `game_background: true`:
![](screenshots/game-bg.png)

```yaml
entities:
  - sensor.steam_<steam-id>
  - sensor.steam_<steam-id>
  - sensor.steam_<steam-id>
friendly_name: hello
game_background: true
type: 'custom:kb-steam-card'
```

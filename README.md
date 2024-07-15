# Notice
This is currently not being worked on for more features but I am happy to accept any pull requests.

# Lovelace Love-Lock-Card
Custom Lovelace card to password protect or lock entire Home Assistant cards. Based upon vertical-stack-in-card. 
This is not a bulletproof method and is just an implementation of [client-side security](https://i.redd.it/1iavece0fp111.jpg). But could be useful against children or flatmates poking where they shouldn't.  


#### Please ⭐️ this repo if you find it useful


# Example
There are 3 types of locks. Locks are activated when clicking on any card.

***Left*** - Password Protected.

***Middle*** - Timeout to fade.

***Right*** - Confirm Unlock


![example](https://i.imgur.com/k35TSKw.gif)

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:love-lock-card`
| cards | list | **Required** | List of cards
| title | string | **Optional** | Card title
| popup | string | **Optional** | password, confirm, timeout
| password | string | **Required** | Only required with popup:password

## Installation

### Now available in HACS

![HACS](https://i.imgur.com/1xNjAuC.jpg)

### Manual Install

1. Install the `love-lock-card` card by copying `love-lock-card.js` to `<config directory>/www/love-lock-card.js`

2. Link `love-lock-card` inside your `ui-lovelace.yaml` 

```yaml
resources:
  - url: /local/love-lock-card.js
    type: js
```

3. Add a custom card in your `ui-lovelace.yaml`

**Password Example**

```yaml
type: 'custom:love-lock-card'
title: Lounge
popup: password
password: 1234
cards:
  - entity: light.hue_white_lamp_1
    name: Lounge Lamp
    type: light
```

**Confirm Example**

```yaml
type: 'custom:love-lock-card'
title: Lounge
popup: confirm
cards:
  - entity: light.hue_white_lamp_1
    name: Lounge Lamp
    type: light
```

**Timeout Example**

```yaml
type: 'custom:love-lock-card'
title: Lounge
popup: timeout
cards:
  - entity: light.hue_white_lamp_1
    name: Lounge Lamp
    type: light
```

# Credits
Idea comes from [Thomasloven's lovelace-toggle-lock-entity-row](https://github.com/thomasloven/lovelace-toggle-lock-entity-row)

Based on [vertical-stack-in-card](https://github.com/custom-cards/vertical-stack-in-card/blob/master/README.md)

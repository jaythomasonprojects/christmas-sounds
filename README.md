# Christmas Sounds

## Description

This project is a soundboard application built with React. It allows users to play different sounds, and display a unique Christmas greeting/message. The sounds and greetings can be customised, so you can make your own soundboard to share. You can use sites like [this one](https://www.qr-code-generator.com/) to create a QR code that links to your soundboard with the recipient's name in the URL, so you could add it to a Christmas card (that's how I'm using it).

## Instructions for Use

### Editing Sounds

Sounds in this application are categorized into two types: sprites and tracks.

#### Sprites

Sprites are added to the sound board at the top of the app. Each sprite is represented as an object in the `sprites` array in the `sounds.js` file. The `src` attribute for a sprite is an array, meaning a sprite can contain multiple sound files. If a sprite does contain multiple sound files, when the sprite button is pressed, it will play one at random.

```javascript
{
  name: 'Sprite Name',
  src: ['/assets/sounds/sound-file1.mp3', '/assets/sounds/sound-file2.mp3']
  type: 'sprite'
}
```

#### Tracks

Tracks are added to the mixer, below the soundboard.

```javascript
{
  name: 'Track Name',
  src: '/assets/sounds/sound-file.mp3'
  type: 'track'
}
```

### Editing Greetings

Greetings are defined in the `greetings.js` file in the `src/components/Modal/` directory. Each greeting is an object in the `greetings` array.

- `name`: The URL parameter. If this name is found in the URL, this greeting object will be used.
- `fullName`: The name that will be displayed in the greeting. This allows `name` to be an 'alias', so you can add a real name here.
- `message`: The greeting message to be displayed. This must be defined, but if it is a blank string `''`, it will default to the default greeting message defined in the 'modal.jsx' component.

```javascript
{
  name: 'alias',
  fullName: 'Real Name',
  message: 'Hello, world!'
}
```

### Appending a Name to the URL

To append a name to the URL, simply add `/?name=` followed by the name to the end of the URL address.

For example, if you want to share your soundboard with "John", you would append `/?name=John` to the end of the URL. (eg. `https://www.example.com/?name=John`)


## Credits

This project uses the following assets and technologies:

- React: A JavaScript library for building user interfaces.
- Vite: A build tool that aims to provide a faster and leaner development experience for modern web projects.
- Howler.js: A JavaScript audio library for the modern web.
- Icons from [Flaticon](https://www.flaticon.com/): Free icons used under the [Flaticon Basic License](https://support.flaticon.com/s/article/Personal-use-FI?language=en_US).
- Sounds from [Zapsplat](https://www.zapsplat.com/): Free sounds used under the [Zapsplat Standard License](https://www.zapsplat.com/license/).
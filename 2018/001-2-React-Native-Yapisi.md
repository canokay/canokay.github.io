# React Native Yapisi
React Native de ki sayfa yapıları html sayfa yapılarına benzer.

İlk başta htmldeki `<head> </head>` blokları gibi import kısmı

Örnek:
``` javascript
import React, { Component } from 'react';
```

Daha sonra `<body> </body>` blokları gibi Component Bölümü

Örnek: 
``` javascript
type Props = {};
export default class App extends Component<Props> {
  render() {
    return (
        <Text>
          Merhaba Dünya!
        </Text>
    );
  }
}
```
En sonunuda bu html olmasada Render bölümü

Örnek:
``` javascript
AppRegistry.registerComponent('ornekproje', () => App);
```

Bu yüzden web developerlıktan (benim gibi) React Native geçen arkadaşlar çok kolay anlayacaklardır. Fakat direkt çok az javascript bilgisi ile başlamanızı önermem. İlk başta diğerki native diller gibi Android veya iOS'e bakmanızı, en azından çalışma mantığını öğrenmenizi öneririm. 

# moviles-react-notificationes

1. Crear un nuevo proyecto
```
   npx create-expo-app notificaciones-app --template
```

El template a escoger será **Blank**

2. Instalar dependencias
```
npx expo install expo-router react-native-safe-area-context react-native-screens @react-native-async-storage/async-storage
```

3. Instalar React Native Paper
```
npx expo install react-native-paper react-native-vector-icons
```

4. Abrir en Expo Go

⚠️ Debes ver la app en tu celular

---

Instalar
```
npx expo install expo-notifications
```

En App.js

```javascript
import { View, Text, Button } from 'react-native';
import * as Notifications from 'expo-notifications';
```

Otorgar permisos
```
const pedirPermiso = async () => {
  await Notifications.requestPermissionsAsync();
};

```

Agregar método para notificar
```javascript
const enviarNotificacion = async () => {
  await Notifications.scheduleNotificationAsync({
    content: {
      title: "Hola, mundo 🌍",
      body: "Esta es tu primera notificación",
    },
    trigger: null, // Este trigger lo puedes modificar para darle unos segundos de delay, ejemplo: trigger{ seconds: 5 }
  });
};

```

UI:
```
<View style={{ marginTop: 50 }}>
      <Text>Notificaciones</Text>

      <Button title="Pedir permiso" onPress={pedirPermiso} />
      <Button title="Enviar notificación" onPress={enviarNotificacion} />
    </View>
  );
```

⚠️ Esto no funciona bien en el navegador, preferentemente usa Android o iOS (puede pedir permisos)


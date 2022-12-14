# NLW eSports - Mobile
## Criação de Projeto
Execute no `PowerShell`:
```
expo init mobile
```
Sendo `mobile` o nome do diretório que será inciado o projeto

## Splash Art
Use este projeto no [Figma](https://www.figma.com/file/ddc0glVeILssZl0Dcn1lSS/App-Icon-%26-Splash) para criar uma `Splash Art`

## R Component - Extensão de Snipets
`rodrigorgtic.rcomponent`

## Google Fonts
### Instalação
Execute no `PowerShell`:
```
npx expo install expo-font @expo-google-fonts/inter
```
## Safe Area Context
### Instalação
Execute no `PowerShell`:
```
npx expo install react-native-safe-area-context
```
## Linear Gradient
### Instalação
Execute no `PowerShell`:
```
npx expo install expo-linear-gradient
```
## React Navigator - Páginação
### Instalação
Execute no `PowerShell`:
```
npm i @react-navigation/native
npx expo install react-native-screens
npm i @react-navigation/native-stack
```

## Phospor - Ícones
### Instalação
Execute no `PowerShell`:
```
npm i --save phosphor-react-native
npx expo install react-native-svg
```

## Clipboard - Copiar para área de transferência
### Instalação
Execute no `PowerShell`:
```
npx expo install expo-clipboard
```

## Notifications - Notificações
### Instalação
Execute no `PowerShell`:
```
npx expo install expo-notifications
```
### Configuração
crie `/src/services/notificationsConfig.ts` e `/src/services/getPushNotificationToken.ts`
#### notificationsConfig.ts
```
import * as Notifications from 'expo-notifications';
Notifications.setNotificationHandler({
    handleNotification: async () => ({
        shouldShowAlert: true,
        shouldPlaySound: true,
        shouldSetBadge: true
    })
});
```
#### getPushNotificationToken.ts
```
import * as Notifications from 'expo-notifications';
export async function getPushNotificationToken() {
    const { granted } = await Notifications.getPermissionsAsync();
    if (!granted) {
        await Notifications.requestPermissionsAsync();
    }
    
    if (granted) {
        const pushToken = await Notifications.getExpoPushTokenAsync();
        console.log('NOTIFICATION TOKEN =>', pushToken.data);
        
        return pushToken.data;
    }
}
```

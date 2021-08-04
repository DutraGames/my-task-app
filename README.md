# My task app React Native

![GitHub](https://img.shields.io/github/license/Dutragames/my-task-app?style=plastic)
![GitHub top language](https://img.shields.io/github/languages/top/dutragames/my-task-app?style=plastic)

## Description 📰

App in react Native, [My task](https://play.google.com/store/apps/details?id=com.lutrizstudios.mylist), to-do list

## 👨‍💻Technology:

* [expo](https://expo.dev/)
* [ReactJS](https://pt-br.reactjs.org/)
* [React Native](https://reactnative.dev/)

### 📖Libs:

* [animatable](https://github.com/oblador/react-native-animatable)
* [AsyncStorage](https://react-native-async-storage.github.io/async-storage/docs/usage/)
* [picker](https://github.com/react-native-picker/picker)
* [AppIntroSlider](https://github.com/Jacse/react-native-app-intro-slider)

### 📚Dependencies version:

![GitHub package.json dependency version (prod)](https://img.shields.io/github/package-json/dependency-version/DutraGames/my-task-app/react)
![GitHub package.json dependency version (prod)](https://img.shields.io/github/package-json/dependency-version/DutraGames/my-task-app/react-dom)
![GitHub package.json dependency version (prod)](https://img.shields.io/github/package-json/dependency-version/DutraGames/my-task-app/expo)

## 📷Images:

<img src="assets/intro1.png" alt="intro1" width="192" height="406" style="width-max: 100%;"></img>
<img src="assets/intro2.png" alt="intro2" width="192" height="406" style="width-max: 100%;"></img>
<img src="assets/intro3.png" alt="intro3" width="192" height="406" style="width-max: 100%;"></img>

**Application intro screens. They're even on the app's Slider.**

<img src="assets/splash.png" alt="splash" width="192" height="406" style="width-max: 100%;"></img>

**The expo app requires a pre-configured splash screen, in the app I use this one, referring to my [youtube channel](https://www.youtube.com/lutriz)**

## 💻Code:

**As I used some libraries, not necessarily native for expo or React Native, I will leave here part of the code in which I use them.**

### **picker**

``` js
import React, {useState} from 'react';
import {Picker} from '@react-native-picker/picker';

 const [pickerSelect, setPickerSelect] = useState('Simples')
 
  <Picker style={{width:300}}
  selectedValue={pickerSelect}
  onValueChange={(itemValue, itemIndex) => setPickerSelect(itemValue)}>
    <Picker.Item label="Simples" value="Simples" />
     <Picker.Item label="Importante" value="Importante" />
     <Picker.Item label="Muito Importante" value="Muito Importante" />
  </Picker>
```

### **AsyncStorage**

``` js
import React, {useEffect} from 'react';
import AsyncStorage  from  '@react-native-async-storage/async-storage';

  useEffect(() => { 
    async function LoadStorage(){
       const StorageTarefa = await AsyncStorage.getItem('@tarefas')
  
       if(StorageTarefa){
         setTarefa(JSON.parse(StorageTarefa))
       }
    }
  
    LoadStorage()
  }, [])
  
  useEffect(() => {
  async function SaveStorage(){
    await AsyncStorage.setItem('@tarefas', JSON.stringify(tarefa))
  }

  SaveStorage()

  }, [tarefa])


  useEffect(() => { 
    async function LoadApp(){
       const StorageIntro = await AsyncStorage.getItem('@intro')
  
       if(StorageIntro){
         setApp(JSON.parse(StorageIntro))
       }
    }
  
    LoadApp()
  }, [])

  useEffect(() => {
    async function SaveIntro(){
      await AsyncStorage.setItem('@intro', JSON.stringify(app))
    }
  
    SaveIntro()
  
    }, [app])

```

---
**NOTE**

**tarefa** is a state in the code, I recommend that you see the complete code [by clicking here](https://github.com/DutraGames/my-task-app/blob/main/App.js)

---

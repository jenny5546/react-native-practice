# 개발 팁 정리해두기

## Tag 정리
<View> :약간 div같은 느낌인듯
<StatusBar>:위에 시간, 배터리 뜨는 상단바,
<Text>: div인데 텍스트부분들때? 제목같은거할때

## CSS 먹이기
```javscript
const styles = StyleSheet.create({
  container: {
    어쩌고저쩌고.
  },
  title: {
    어쩌고저쩌고
  },
})
// jsx에서 먹일 때는:
<Text style={styles.title}>Kawai To Do</Text>
```
### platform specific 한 css는?
> shadow는 ios, android 먹이는 방법이 다르다.

```javscript
Platform.select({
    ios: {

    },
    android: {

    }
})
```
### 화면의 width, height 갖고오기
`import {Dimensions} from "react-native";`
`const { height, width } = Dimensions.get("window");`
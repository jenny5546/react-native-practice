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
> shadow는 ios, android 먹이는 방법이 다르다. 필요하면 코드 참고

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

### Textinput에서 Props returnKeyType
다 입력하고 나서 enter, go 같이 다 입력했을 때 뜨는 값을 설정할 수 있음 
종류:
1. done
2. go
3. next
4. search
5. send

### <View> vs <ScrollView>
- View (Fixed)
- ScrollView 말그대로 스크롤해서 내릴 수 있는 것. 

ScrollView 안에 있는 것들에 style을 먹이고 싶을 때는, 
`contentContainerStyles = {styles.toDos}` 이렇게!

### <TouchableOpacity>

check box 나 똥그라미 같은거 구현할때
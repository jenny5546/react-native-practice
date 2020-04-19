# 개발 팁 정리해두기

## Tag 정리
<View> :약간 div같은 느낌인듯
<StatusBar>:위에 시간, 배터리 뜨는 상단바,
<Text>: div인데 텍스트부분들때? 제목같은거할때

## CSS 먹이기
```javascript
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

```javascript
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

### View vs ScrollView
- View (Fixed)
- ScrollView 말그대로 스크롤해서 내릴 수 있는 것. 

ScrollView 안에 있는 것들에 style을 먹이고 싶을 때는, 
`contentContainerStyles = {styles.toDos}` 이렇게!

### <TouchableOpacity>

check box 나 똥그라미 같은거 구현할때,
props: onPress = {} 로 state 설정 가능!

### How to Pass multiple styles in one component depending on the state?
이렇게 array 형태로! 여러개를 넣어두고 상황에 따라 다르게 할 수 있음. 
```javascript
    <View
        style={[
        styles.circle,
        isCompleted ? styles.completedCircle : styles.uncompletedCircle
        ]}
    />
    //styles
    circle: {
        width: 30,
        height: 30,
        borderRadius: 15,
        borderWidth: 3,
        marginRight: 20
    },
    completedCircle: {
        borderColor: "#bbb"
    },
    uncompletedCircle: {
        borderColor: "#F23657"
    },
```
### Flex Container 복습
```
container: {
    flexDirection: "row", //content 들을 옆으로
    alignItems: "center", // container의 중간에
    justifyContent: "space-between" //거리는 좀 띄고
},
```

### 버튼 주위를 눌러도 터치 인지되게 하기 위해서 
그 버튼의 container (한 버튼의) 에다가 
```
  actionContainer: {
    marginVertical: 10,
    marginHorizontal: 10
  },
```
이렇게 먹여서 주위를 터치해도 먹어지게끔 설정하기.->두꺼운 손가락을 위한 배려

### onBlur (TextInput의 Props)

다른 곳을 눌렀을 때, 이 event를 onBlur로 감지해서 이벤트핸들링 할 수 있음. 예를 들어
저장이 된다거나, 나간다거나 등등.
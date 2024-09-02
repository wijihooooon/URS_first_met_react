# 12장 State 끌어올리기
- **Shared state**
    - **하위 컴포넌트**가 **공통된 부모 컴포넌트**의 **state**를 공유하며 사용하는 것
    
    ![Shared State.jpg](/URS_first_met_react/12장%20State%20끌어올리기/images/Shared%20State.jpg)
    
- **state 끌어올리기**
    - **하위 컴포넌트**의 **state**를 **공통된 부모 컴포넌트**로 끌어올려서 공유하는 방식
    - state에서 가져오는 것이 아닌 props를 통해서 가져오게 된다. 컴포넌트의 state를 사용하지 않게 되기 때문에 입력값이 변경되었을 때 상위 컴포넌트로 변경된 값을 전달해 주어야 하기 때문에 handleChange() 함수를 변경

```jsx
const handleChange = (event) => {
	//변경 전: setTemperature(event.target.value)
	props.onTemperatureChange(event.target.value)
}

return(
	//변경 전: <input value={temperature} onChange={handleChange}/>
	<input value={props.temperature} onChange={handleChange}/>
)
```
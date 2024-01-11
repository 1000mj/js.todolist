# <a href="" target="_blank">사이트 바로가기</a>

## 1.프로젝트 목표
- 자바스크립트만 사용해서 todo-list구현하기
## 2.프로젝트에 사용한 기술
- html
- css
## javaScript
### 로컬스토리지에 저장
###  saveTask() , loadTasks()

```js
function saveTasks() {
	var taskList = document.getElementById('taskList').innerHTML;
    localStorage.setItem('tasks', taskList);
    }
function loadTasks() {
	var savedTasks = localStorage.getItem('tasks');
    if (savedTasks) {
    	document.getElementById('taskList').innerHTML = savedTasks;
    }

```
#### saveTask()
- 이 함수는 현재 작업 상태를 로컬 스토리지에 저장하는 역할을 합니다
- `taskList` 엘리먼트의 innerHTML을 가져와서 로컬 스토리지에 저장합니다
#### loadTask()
- 이 함수는 DOM 콘텐츠가 완전히 로드될 때 호출됩니다
-  `LocalStorage.getItem('tasks')` 를 사용하여 로컬 스토리지에 저장되어있는 작업을 가져옵니다
- 저장된 작업이 있으면 `taskList` 엘리먼트의 innerHTML을 저장된 작업으로 설정합니다


###  할 일 추가

### addTask()
```js
function addTask() {
	var taskInput = document.getElementById('taskInput');
    var taskList = document.getElementById('taskList');
    var newTask = document.createElement('li');
    newTask.innerHTML = taskInput.value + ' <button onclick="deleteTask(this)">x</button>';
    taskList.appendChild(newTask);
    saveTasks();
    taskInput.value = '';
    }
```

- 이 함수는 사용자가 할 일을 추가할 때 호출됩니다
- `taskInput` , `taskList` 엘리먼트를 사용하여 새로운 할 일 항목을 만듭니다
- 생성된 할 일 항목을 `taskList`에 추가하고, 작업을 저장하기 위해 `saveTasks()` 함수를 호출합니다
- 추가 버튼을 누르면 `taskInput`의 값을 비워(`taskInput.value = '';`) 사용자가 다음 할 일을 쉽게 입력할 수 있도록 합니다

###  할 일 삭제
### deleteTask()

```js
function deleteTask(task) {
	task.parentNode.remove();
    saveTasks();
}
```

- 이 함수는 사용자가 할 일을 삭제할 때 호출됩니다.
- 클릭된 삭제 버튼이 속한 할 일 항목을 찾아 제거하고, 작업을 저장하기 위해 saveTasks() 함수를 호출합니다.

### 오늘 날짜 표시
```js
document.addEventListener('DOMContentLoaded', function () {
	var today = new Date();
    var formattedDate =
    	today.getFullYear() + '년 ' + (today.getMonth() + 1) + '월 ' + today.getDate() + '일';

    document.getElementById('todayDate').textContent = formattedDate;
});
```
- 현재 날짜를 표시하는 역할을 합니다.
- DOMContentLoaded 이벤트가 발생하면 현재 날짜를 가져와서 `todayDate` 엘리먼트의 텍스트로 설정합니다.
## 3.프로젝트 기능설명


## 4.알게된점
- 순수 자바스크립트 되새김에 도움을주었다

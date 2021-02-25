# React

<!-- ## 용어
**Markup**: 디자인을 HTML, CSS로 변환 하는 과정 또는 HTML 파일을 뜻함. HTML, CSS로 변환 된다. 퍼블리싱이라고도 함.

**Markdown**: 주로 README.md 파일로 많이 쓰이고, 현재 이 문서도 Markdown으로 만들어짐. 화려한 레이아웃 업이 Text로 정보 전달 할때 많이 사용한다. -->

## Node.js
https://nodejs.org

## NVM (Node Version Manager)
Node.js 버전을 관리하는 프로그램, 어느 버전이든 설치, 변경, 삭제 가능하다.

<!-- **Mac OS Node 삭제 방법**: https://gomugom.github.io/how-to-remove-node-from-macos/ -->

<!-- **VSCode에서 터미널 호출시 버전을 못 찾을 때**: https://github.com/Microsoft/vscode-docs/blob/master/docs/editor/integrated-terminal.md#why-is-nvm-complaining-about-a-prefix-option-when-the-integrated-terminal-is-launched
```sh
# nvm is not compatible with the npm config "prefix" option: currently set to "/usr/local"
# Run `npm config delete prefix` or `nvm use --delete-prefix v8.12.0 --silent` to unset it.
## nvm 설치 전에 npm이 설치되어서 문제가 발생 한다.
ls -la /usr/local/bin | grep npm
rm -R /usr/local/bin/npm /usr/local/lib/node_modules/npm/bin/npm-cli.js
``` -->

<!-- **nvm 삭제 방법**:
```sh
rm -rf ~/.nvm
rm -rf ~/.npm
rm -rf ~/.bower
``` -->

<details><summary>Mac OS</summary>
https://github.com/nvm-sh/nvm

https://gist.github.com/falsy/8aa42ae311a9adb50e2ca7d8702c9af1
```sh
# 설치
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash

# vi 에디터 실행
vi ~/.bash_profile

# 해당 경로 적용 시키키
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

# ~/.bash_profile 재 실행 시키기
source ~/.bash_profile
```
</details>

Windows

https://github.com/coreybutler/nvm-windows/releases

```sh
# 설치 된 node.js 리스트를 본다.
nvm ls

# 해당 버전을 설치 한다.
nvm install 14.15.5

# 해당 버전을 삭제 한다.
nvm uninstall 14.15.5

# 해당 버전을 사용 한다.
nvm use 14.15.5

# 기본 버전 변경 하기
nvm alias default 14.15.5
```

<!-- ## Visual Studio Code
**Tab 스페이스 2칸으로 설정**: Preferences > 검색 > editor.detectIndent

https://stackoverflow.com/questions/29972396/how-to-set-tab-space-style

기본 텝 사이즈를 2칸으로 변경한다.
```json
"editor.tabSize": 2
```

해당 파일의 텝 사이즈를 무시하고 기본 텝 사이즈로 설정한다.
```json
"editor.detectIndentation": false
``` -->

## Create React App 설치
https://github.com/facebook/create-react-app
```sh
# React의 스케폴딩을 쉽게 만들고 작업 후 쉽게 빌드 할 수 있다.
# npx는 npm v.5.2 이후 부터 npm과 같이 설치 된다.
npx create-react-app react-study

# VSCode로 해당 디렉토리 열기
npm run build
npm install -g serve
serve -s build

## 프로젝트 실행
npm start
```

<!-- # redux 사용
npx create-react-app my-app --template redux -->

## GIT
소스 관리를 위해 사용한다. 어느 파일이 언제 어떻게 변경 되었는지 쉽게 볼 수 있다.

**GIT 설치**

**VSCode 확장 Git Graph 설치**

<!-- ## 현재 문서 Git clone 하기

git clone https://github.com/ovdncids/react-curriculum.git

## Git .gitignore
```sh
# npm or yarn
package-lock.json
yarn.lock

# .idea
.idea
```

**lock 파일**: 가끔 이 파일 때문에 클라이언트와 서버 사이에 버전이 안 맞아서 오류가 발생한다.
용량도 크고 npm install 할때 마다 생성되는 파일이니 .gitignore 목록에 넣는다.

**package-lock.json, yarn.lock 파일 삭제**

**Git push**
```sh
git push
```

**commit 이름 수정**
```sh
git commit --amend -m ""
```

**commit 취소**
```sh
git reset HEAD~
``` -->

<!-- **첫 commit 취소**
```sh
git update-ref -d HEAD
``` -->

<!-- **이전 commit과 합치기**
```sh
git rebase -i HEAD~2
# 2번째 줄 pick을 fixup으로 바꾸고 저장
``` -->

<!-- **이전으로 돌아가 수정 하기**
```sh
# 첫 commit 수정
git rebase -i --root $tip
# 이후 commit 수정
git rebase -i HEAD~2
  pick -> edit 수정
원하는 파일 수정
git add .
git rebase --continue
``` -->

## Sass 설치
css를 프로그램화 하여 색상 테마를 변수에 넣을 수 있고, 반복 부분을 저장하고 불러 올 수 있다. 이름은 Sass지만 파일명은 scss이다.

https://sass-guidelin.es/ko
```sh
npm install sass sass-loader
```

## 필요 없는 파일 지우기
```diff
- src/App.css
- src/App.test.js
- src/index.css
- src/logo.svg
```

## Markup
src/App.js
```diff
- import logo from './logo.svg';
- import './App.css';
```
```js
<div>
  <header>
    <h1>React study</h1>
  </header>
  <hr />
  <div className="container">
    <nav className="nav">
      <ul>
        <li><h2>Members</h2></li>
        <li><h2>Search</h2></li>
      </ul>
    </nav>
    <hr />
    <section className="contents">
      <div>
        <h3>Members</h3>
        <p>Contents</p>
      </div>
    </section>
    <hr />
  </div>
  <footer>Copyright</footer>
</div>
```

src/index.scss
```scss
body {
  margin: 0;
}

// common
.pointer {
  cursor: pointer;
}

.relative {
  position: relative;
}

.d-none {
  display: none;
}

.d-block {
  display: block;
}

.flex {
  display: flex;
}

// Markup
hr {
  display: none;
}

h1, footer {
  margin: 0.5rem;
}

.container {
  @extend .flex;
  min-height: 300px;
  border-top: 1px solid #ddd;
  border-bottom: 1px solid #ddd;
  .nav {
    min-height: 300px;
    background-color: skyblue;
    ul {
      list-style: none;
      margin: 0.5rem 0 0.5rem 0;
      padding: 0;
      h2 {
        margin: 0;
        padding: 0.5rem;
      }
    }
  }
  .contents {
    margin-left: 1rem;
  }
}
```

src/index.js
```diff
- import './index.css';
+ import './index.scss';
```

<!-- ## CSS Flex
https://opentutorials.org/course/2418/13526

https://www.youtube.com/watch?v=eprXmC_j9A4

**현재 브라우저 상황**: YouTube IE11 부터 지원. IE11 부터 Flex 사용 가능. -->

## React Component 만들기
Header, Nav, Footer 이렇게 Component 별로 파일을 나눈다.

src/App.js
```js
import Header from './component/Header.js';
import Nav from './component/Nav.js';
import Footer from './component/Footer.js';
```
```diff
- <header>
-  <h1>React study</h1>
- </header>
+ <Header></Header>

- <nav className="nav">
-   <ul>
-     <li><h2>Members</h2></li>
-     <li><h2>Search</h2></li>
-   </ul>
- </nav>
+ <Nav></Nav>

- <footer>Copyright</footer>
+ <Footer></Footer>
```

src/component/Header.js
```js
function Header() {
  return (
    <header>
      <h1>React study</h1>
    </header>
  )
}

export default Header;
```

## React Router DOM 설치
https://reacttraining.com/react-router
```sh
npm install react-router-dom
```

## Router 만들기
src/App.js
```js
import { BrowserRouter, Switch, Route, Redirect } from 'react-router-dom';
import Members from './component/contents/Members.js';
import Search from './component/contents/Search.js';

<BrowserRouter>
  <Switch>
    <Route exact={true} path="/members" render={props => <Members {...props} testProps={true} />} />
    <Route exact={true} path="/search" component={Search} />
    <Redirect to={{pathname: "/members"}} />
  </Switch>
</BrowserRouter>
```
```diff
- <div>
-   <h3>Members</h3>
-   <p>Contents</p>
- </div>
```

src/component/contents/Members.js
```js
function Members(props) {
  console.log(props);
  return (
    <div>
      <h3>Members</h3>
      <p>Contents</p>
    </div>
  )
}

export default Members;
```
**render, props 풀어서 설명 하기**
**router를 타이핑으로 바꾸어 보기**

src/components/Nav.js
```js
import { Link } from 'react-router-dom';

<li><h2><Link to="members">Members</Link></h2></li>
<li><h2><Link to="search">Search</Link></h2></li>
```
**You should not use `<Link>` outside a `<Router>` 설명하기**

<!-- history.push 자식으로 넘기기
```js
<A1 {...props}></A1>

function A1(props) {
  return (
    <button onClick={() => {props.history.push('/b')}}>
      A1
    </button>
  );
}
``` -->

<!-- **BrowserRouter와 HashRouter 차이점**: BrowserRouter 사용 할 경우 IE9 이전 브라우저에서 오류가 발생 해서 HashRouter를 써야함 -->

**여기 까지가 Markup 개발자 분들이 할일 입니다.**

## CRUD Conpenent Markup
src/components/contents/CRUD.js
```js
class CRUD extends React.Component {
  render() {
    return (
      <div>
        <h3>CRUD</h3>
        <hr className="d-block" />
        <div>
          <h4>Read</h4>
          <table>
            <thead>
              <tr>
                <th>Name</th>
                <th>Age</th>
                <th>Created Date</th>
                <th>Modify</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>횽길동</td>
                <td>39</td>
                <td>2018-10-04</td>
                <td>
                  <button>Update</button>
                  <button>Delete</button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        <hr className="d-block" />
        <div>
          <h4>Create</h4>
          <input type="text" placeholder="Name" />
          <input type="text" placeholder="Age" />
          <button>Create</button>
        </div>
      </div>
    );
  }
}
```

## MobX 설치
https://github.com/mobxjs/mobx
```sh
npm install --save mobx mobx-react
```

## CRUD Store 만들기
**Store 개념 설명**

Component는 상하, 수직, 부모 자식 관계인데 Store는 수평, 평등 관계이다.

src/shared/stores/CRUDStore.js
```js
import { observable, decorate } from 'mobx';

export default class CRUDStore {
  member = {
      name: '',
      age: ''
  }

  // create() {
  //   console.log('create')
  // }
}

decorate(CRUDStore, {
  member: observable
})

export const crudStore = new CRUDStore();
```

<!-- ## VSCode experimentalDecorators 에러 발생시
tsconfig.json
```json
{
  "compilerOptions": {
    "experimentalDecorators": true,
    "allowJs": true
  }
}
```
-->

**CRUD Store 등록하기**
src/index.js
```js
import { Provider } from 'mobx-react';
import { crudStore } from './shared/stores/CRUDStore';

<Provider
  crudStore={crudStore}
>
  <App />
</Provider>
```

## CRUD Conpenent Store inject & observer
src/components/contents/CRUD.js
```js
import { inject, observer } from 'mobx-react';

create() {
  const { crudStore } = this.props;
  crudStore.create();
}

const { crudStore } = this.props;
const { member } = crudStore;

<input
  type="text" placeholder="Name" value={member.name}
  onChange={e => {member.name = e.target.value}}
/>
<input
  type="text" placeholder="Age" value={member.age}
  onChange={e => {member.age = e.target.value}}
/>
<button onClick={() => this.create()}>Create</button>

// Life cycle
componentDidMount() {
  const { crudStore } = this.props;
  const { member } = crudStore;
  member.name = '';
  member.age = '';
}

CRUD = inject('crudStore')(observer(CRUD));
```

**render 함수 설명 하기**

**debugger 설명**
```js
debugger;
```

## Axios(서버 연동), toastr(메시지 창), spin.js(로딩 스피너), nprogress(프로그래스 바), lodash(배열, 오브젝트 유틸리티), moment(시간관련 유틸리티) 설치
```sh
npm install --save axios toastr spin.js nprogress lodash moment
```

## Validation with toastr
https://github.com/CodeSeven/toastr

src/shared/utils.js
```js
import Toastr from 'toastr';
import 'toastr/build/toastr.min.css';

export const toastr = () => {
  return Toastr;
};
Toastr.options.closeButton = true;
Toastr.options.hideDuration = 200;
```

src/shared/stores/CRUDStore.js
```js
import * as utils from '../utils';

// validation
if (!this.member.name) {
  utils.toastr().warning('Please text your name.');
  return;
}
if (!Number(this.member.age) || Number(this.member.age) <= 0) {
  utils.toastr().warning('Please text your age and upper than 0.');
  return;
}
```

## Spin.js
https://spin.js.org/

src/shared/utils.js
```js
import { Spinner } from 'spin.js';
import 'spin.js/spin.css';

export const spinner = () => {
  return new Spinner({scale: 0.5});
};
```

src/components/contents/CRUD.js
```js
create(spinnerTarget) {
  const { crudStore } = this.props;
  crudStore.create(spinnerTarget);
}
```
```js
<button className="relative pointer" onClick={e => this.create(e.target)}>Create</button>
```

src/shared/stores/CRUDStore.js
```js
create(spinnerTarget) {
  utils.spinner().spin(spinnerTarget);
}
```

## node.js 서버 실행
```sh
npm install -g nodemon
nodemon index.js
```

## Axios 서버 연동
https://github.com/axios/axios

### Create
src/shared/utils.js
```js
export const apiCommonError = (error, spinner) => {
  console.log(error);
  console.log(error.response);
  const errMessage = (error.response && error.response.data && (error.response.data.message || error.response.data.errMessage || error.response.data.sqlMessage)) || error;
  toastr().error(errMessage);
  if (spinner) {
    spinner.stop();
  }
};
```

src/shared/stores/CRUDStore.js
```js
import axios from 'axios';

const spinner = utils.spinner().spin(spinnerTarget);
axios.post('http://localhost:3100/api/v1/member', this.member).then(response => {
  console.log(response);
  spinner.stop();
  utils.toastr().success(response.data.result);
  this.read();
}).catch(error => {
  utils.apiCommonError(error, spinner);
});

read() {}
```

### Read
**nprogress**: https://github.com/rstacruz/nprogress

src/shared/utils.js
```js
import * as NProgress from 'nprogress';
import 'nprogress/nprogress.css';

export const apiCommonError = (error, spinner) => {
  nProgress.done();
}

export const nProgress = {
  start: () => NProgress.start(),
  done: () => NProgress.done()
};
```

src/shared/stores/CRUDStore.js
```js
import { decorate, observable, action } from 'mobx';

members = []

read() {
  utils.nProgress.start();
  axios.get('http://localhost:3100/api/v1/member').then(response => {
    console.log(response);
    this.members = response.data.members;
    utils.nProgress.done();
  }).catch(error => {
    utils.apiCommonError(error);
  });
}

decorate(CRUDStore, {
  member: observable,
  members: observable,
  read: action
})
```

src/components/contents/CRUD.js
```js
import _ from 'lodash';
import moment from 'moment';

const { member, members } = crudStore;

{_.map(members, (member, key) => (
  <tr key={key}>
    <td>{member.name}</td>
    <td>{member.age}</td>
    <td>{moment(member.createdDate).format('YYYY-MM-DD HH:mm')}</td>
    <td>
      <button>Update</button>
      <button>Delete</button>
    </td>
  </tr>
))}

crudStore.read();
```

### Update
src/components/contents/CRUD.js
```js
update(spinnerTarget, key) {
  const { crudStore } = this.props;
  crudStore.update(spinnerTarget, key);
}
```
```js
<input
  type="text" placeholder="Name" value={member.name}
  onChange={e => {member.name = e.target.value}}
/>

<input
  type="text" placeholder="Age" value={member.age}
  onChange={e => {member.age = e.target.value}}
/>

<button className="relative pointer" onClick={e => this.update(e.target, key)}>Update</button>
```

src/shared/stores/CRUDStore.js
```js
update(spinnerTarget, key) {
  const member = this.members[key];
  if (!member.name) {
    utils.toastr().warning('Please text your name.');
    return;
  }
  if (!Number(member.age) || Number(member.age) <= 0) {
    utils.toastr().warning('Please text your age and upper than 0.');
    return;
  }
  const spinner = utils.spinner().spin(spinnerTarget);
  axios.put('http://localhost:3100/api/v1/member', {key, member}).then(response => {
    console.log(response);
    spinner.stop();
    utils.toastr().success(response.data.result);
    this.read();
  }).catch(error => {
    utils.apiCommonError(error, spinner);
  });
}
```

### Delete
src/components/contents/CRUD.js
```js
delete(spinnerTarget, key) {
  const { crudStore } = this.props;
  crudStore.delete(spinnerTarget, key);
}
```
```js
<button className="relative pointer" onClick={e => this.delete(e.target, key)}>Delete</button>
```

src/shared/stores/CRUDStore.js
```js
delete(spinnerTarget, key) {
  if (!window.confirm('Are you sure?')) {
    return;
  }
  const spinner = utils.spinner().spin(spinnerTarget);
  axios.delete(`http://localhost:3100/api/v1/member/${key}`).then(response => {
    console.log(response);
    spinner.stop();
    utils.toastr().success(response.data.result);
    this.read();
  }).catch(error => {
    utils.apiCommonError(error, spinner);
  });
}
```

## Search Conpenent Markup
src/components/contents/Search.js
```js
<div>
  <h3>Search</h3>
  <hr className="d-block" />
  <div>
    <input type="text" />
    <button>Search</button>
  </div>
  <hr className="d-block" />
  <div>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Age</th>
          <th>Created Date</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>횽길동</td>
          <td>39</td>
          <td>2018-10-04</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```

## Search Store 만들기
src/shared/stores/SearchStore.js
```js
import { decorate, observable, action } from 'mobx';
import axios from 'axios';
import * as utils from '../utils';

class SearchStore {
  member = {
    name: ''
  }

  members = []

  read() {
    utils.nProgress.start();
    axios.get(`http://localhost:3100/api/v1/search?name=${this.member.name}`).then(response => {
      console.log(response);
      this.members = response.data.members;
      utils.nProgress.done();
    }).catch(error => {
      utils.apiCommonError(error);
    });
  }
}

decorate(SearchStore, {
  member: observable,
  members: observable,
  search: action
})

export const searchStore = new SearchStore();
```

**Search Store 등록하기**
src/index.js
```js
import { searchStore } from './shared/stores/SearchStore';

searchStore={searchStore}
```

## Search Conpenent Store inject & observer
src/components/contents/Search.js
```js
import { inject, observer } from 'mobx-react';
import _ from 'lodash';
import moment from 'moment';

read() {
  const { searchStore } = this.props;
  searchStore.read();
}

keyPress(e) {
  if (e.charCode === 13) {
    this.read();
  }
}

const { searchStore } = this.props;
const { member, members } = searchStore;
```
```js
<input
  type="text" value={member.name}
  onChange={e => {member.name = e.target.value}}
  onKeyPress={(e) => this.keyPress(e)}
/>
<button className="relative pointer" onClick={e => this.read()}>Search</button>

{_.map(members, (member, key) => (
  <tr key={key}>
    <td>{member.name}</td>
    <td>{member.age}</td>
    <td>{moment(member.createdDate).format('YYYY-MM-DD HH:mm')}</td>
  </tr>
))}
```
```js
// Life cycle
componentDidMount() {
  console.log('componentDidMount');
  const { searchStore } = this.props;
  const { member } = searchStore;
  member.name = '';
  searchStore.read();
}

Search = inject('searchStore')(observer(Search));
```

## Search Conpenent 파라미터 변경과 새로고침 적용
src/components/contents/Search.js
```js
import querystring from 'querystring';

read() {
  const { history, searchStore } = this.props;
  const { member } = searchStore;
  history.push(`/search?name=${member.name}`);
}

// Life cycle
componentDidMount() {
  console.log('componentDidMount');
  const { location, searchStore } = this.props;
  // const { member } = searchStore;
  // member.name = '';
  const { name } = querystring.parse(location.search.split('?')[1]);
  searchStore.member.name = name || '';
  searchStore.read();
}

componentWillReceiveProps(nextProps) {
  console.log('componentWillReceiveProps');
  const { searchStore } = this.props;
  const { name } = querystring.parse(nextProps.location.search.split('?')[1]);
  searchStore.member.name = name || '';
  searchStore.read();
}
```

## Proxy 설정
https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#proxying-api-requests-in-development

package.json
```json
"proxy": "http://localhost:3100"
```

모든 파일 수정 하기
```diff
- http://localhost:3100/api
+ /api
```

당황 하지 말고 다시 실행 하기
```sh
npm start
```

<!-- ## Express에 build된 파일 넣기
package.json
```json
"build": "react-scripts build && rm -fr ../express/public && mv build ../express/public",
``` -->

# 수고 하셨습니다.

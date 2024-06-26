# 🐕PetPar
React.js와 Node.js를 이용해 유기동물 관련 사이트를 만들었습니다.

## 프로젝트 소개
PetPar은 React와 Node.js를 활용하여 개발한 반려동물 정보사이트로, 사용자들에게 다양한   
펫 케어 정보를 제공합니다. 직관적이고 사용자 친화적인 UI로 구성되어 있으며, 반려동물을   
사랑하는 이용자들에게 유용한 서비스를 제공합니다.   

[사이트 바로가기](https://petpar.fly.dev/)

## 팀 소개
|김우주|김희진|권초록|이원영|
|:---:|:---:|:---:|:---:|
|<img width="150px" src="https://avatars.githubusercontent.com/u/144635615?v=4" />|<img width="150px" src="https://avatars.githubusercontent.com/u/144635622?v=4">|<img width="150px" src="https://avatars.githubusercontent.com/u/144635615?v=4">|<img width="150px" src="https://avatars.githubusercontent.com/u/135201248?v=4">|
|[@GIT](https://github.com/rlanrid)|[@GIT](https://github.com/seoeugene)|[@GIT](https://github.com/yunyoungsik/)|[@GIT](https://github.com/yunyoungsik/)|

## 🔍주요 기능   
1. 유기동물 정보 제공   

2. 유기동물에 관한 커뮤니티 기능

3. 보호소 위치 및 정보 제공

4. 반려동물에 관한 지식정보 제공

5. 로그인 및 회원가입

6. 실시간 채팅

## 🔨초기 세팅
- client   
`npx create-react-app [폴더명]`   
`npm install axios`   
`npm install firebase`   
`npm install geocoder`   
`npm install moment`   
`npm install react-icons`   
`npm install react-kakao-maps-sdk`   
`npm install react-router-dom`
`npm install react-redux`  
`npm install sass`

- server   
`npm init -y`
`npm install express --save`   
`npm install nodemon --save`   
`npm install path --save`   
`npm install mongoose --save`   
`npm install multer --save`   
`npm install aws-sdk@2.348.0 --save`   
`npm install multer-s3@2.10.0 --save`   
`npm install socket.io --save`   
`npm install cors --save`


## 🧾개념 정리
- **React**   
React는 페이스북에서 개발한 오픈 소스 자바스크립트 라이브러리로,   
사용자 인터페이스를 구축하기 위한 목적으로 만들어졌습니다.   
React는 단일 페이지 어플리케이션(SPA)과 같은 현대적인 웹 어플리케이션을 개발할 때 특히 효과적입니다.   

- **axios**   
axios는 자바스크립트 및 Node.js 환경에서 사용되는 HTTP 클라이언트 라이브러리입니다.    
이 라이브러리는 HTTP 요청을 만들고 응답을 처리하는 데 도움이 됩니다.   
Axios는 Promise 기반으로 동작하며, 비동기적으로 데이터를 주고받을 수 있습니다.   

- **firebase**   
Firebase(파이어베이스)는 Google에서 제공하는 통합 개발 플랫폼으로,    
웹 및 모바일 애플리케이션을 빌드하기 위한 다양한 서비스를 제공합니다.   
Firebase는 사용 편의성과 서로 쉽게 통합되는 특징으로 알려져 있습니다.   

- **express**   
Express는 Node.js를 위한 강력하고 유연한 웹 애플리케이션 프레임워크입니다. Node.js는 자바스크립트를   
사용하여 서버 측 애플리케이션을 개발하기 위한 런타임 환경이며, Express는 이를 효과적으로 활용할 수 있도록 도와줍니다.

- **react-router-dom**   
react-router-dom은 React 기반의 웹 애플리케이션에서 라우팅을 구현하기 위한 라이브러리입니다.   
이 라이브러리는 React 애플리케이션에서 다양한 페이지 간의 네비게이션을 처리하는 데 사용됩니다.   
주로 React 웹 애플리케이션을 개발할 때, 다양한 라우팅 및 네비게이션 요구 사항을 간편하게 다룰 수 있도록 도와줍니다.   

- **redux**   
Redux는 JavaScript 애플리케이션의 상태를 효과적으로 관리하기 위한 상태 관리 라이브러리 중 하나입니다.   
특히 React와 함께 사용되며, 복잡한 상태 로직을 더 효율적으로 다룰 수 있도록 돕습니다.   
Redux는 예측 가능한 상태 컨테이너를 제공하여 상태 관리를 단순하고 투명하게 만듭니다.

- **nodemon**   
nodemon은 Node.js 애플리케이션을 개발하는 데 사용되는 도구로,   
코드 변경을 감지하고 자동으로 서버를 다시 시작하는 기능을 제공합니다.   
이는 애플리케이션을 개발하는 동안 코드를 수정할 때마다 수동으로 서버를 재시작하지 않아도 되게 해주어 개발 효율성을 높여줍니다.

- **mongoose**   
Mongoose는 MongoDB와 상호 작용하기 위한 Node.js 기반의 ODM(Object Data Modeling) 라이브러리입니다.   
MongoDB는 NoSQL 데이터베이스이며, Mongoose는 이를 더 쉽게 사용하기 위한 도구로서 스키마 기반의 데이터   
모델링과 데이터 유효성 검사(validation) 등을 제공합니다.

- **multer**   
Multer는 Node.js의 middleware로, 웹 애플리케이션에서 파일 업로드를 쉽게 처리할 수 있도록   
도와주는 패키지입니다. Multer는 Express.js와 함께 주로 사용되며, 클라이언트에서 서버로   
파일을 전송하고 서버에서 이를 처리하는 데 도움을 줍니다.   

- **socket.io**   
Socket.IO는 실시간 웹 어플리케이션을 구축하기 위한 자바스크립트 라이브러리입니다. 이 라이브러리는 양방향 통신을    가능하게 하는 WebSocket 프로토콜을 기반으로 하며, 실시간 정보 교환에 효과적입니다. 소켓.IO는 서버와 클라이언트 간의   
실시간 양방향 통신을 단순화하고 추상화하여 개발자가 손쉽게 웹 소켓을 사용할 수 있도록 도와줍니다.   

- **cors**    
CORS(Cross-Origin Resource Sharing)는 웹 애플리케이션에서 다른 도메인에 위치한 리소스에 접근할 수 있는   
권한을 부여하기 위한 보안 기능입니다. 웹 브라우저는 보안상의 이유로 기본적으로 동일 출처 정책(Same-Origin Policy)을   
적용하여, 하나의 도메인에서 로드된 문서나 스크립트가 다른 도메인의 리소스에 직접 접근하는 것을 제한합니다.   

## 🌱기여 방법   
**홈**   
   
axios를 이용해 공공데이터포털에서 데이터를 받아오고, setPetItems에 데이터값을 넣어줍니다.   
저장된 데이터를 map문을 활용해 보여줍니다.    

```js
    try {
        const res = await axios.get(url, {
            params: {
                serviceKey: apiKey,
                bgnde: "",
                endde: "",
                pageNo: "1",
                numOfRows: "20",
                _type: "json",
            }
        })

        let items = res.data.response.body.items.item;

        setPetItems(items);
    } catch (err) {
        console.log(err);
    } finally {
        setLoading(false);
    }


    petItems.map((item, key) => (
        ...
    ))
```      
</br>
</br>

**회원가입 및 로그인**   

firebase를 사용하여 사용자를 등록하는 회원가입 기능을 추가했습니다.   
`createUserWithEmailAndPassword` 메서드를 이용해 새로운 사용자를 등록하고,   
새로 생성된 사용자의 프로필을 업데이트하는 `updateProfile` 메서드를 사용합니다.   

```js
    // firebase 회원가입
    let createdUser = await firebase.auth().createUserWithEmailAndPassword(youEmail, youPass);

    await createdUser.user.updateProfile({
        displayName: youName,
        email: youEmail,
        photoURL: "https://kr.object.ncloudstorage.com/petpar-rlan/user/profile.png"
    });

    console.log(createdUser.user);
```   

mongoDB의 경우 `axios`를 이용하여 body의 정보를 서버에 보내고,   
성공적으로 데이터를 저장한 경우 메시지와 함께 /login 페이지로 이동시킵니다.   

```js
    // mongoDB 회원가입
    let body = {
        email: createdUser.user.multiFactor.user.email,
        displayName: createdUser.user.multiFactor.user.displayName,
        uid: createdUser.user.multiFactor.user.uid, // firebase에서 만든 아이디
        photoURL: "https://kr.object.ncloudstorage.com/petpar-rlan/user/profile.png",
    }
```   

로그인은 `signInWithEmailAndPassword` 메서드를 이용해 간편히 기능을 추가할 수 있습니다.   
후에 회원정보는 `redux`를 사용해 관리합니다.   

```js
    try {
        await firebase.auth().signInWithEmailAndPassword(email, password);
        alert("로그인을 했습니다.");
        navigate("/");
    } catch (err) {
        console.log(err);
        setErrorMsg("이메일과 비밀번호를 다시 한번 확인해주세요!");
    }
```   
   
**게시글**   
   
게시글을 작성할 때는 `useState`에 사용자가 입력한 정보(제목, 내용, 카테고리 등)을 저장하고,   
저장한 데이터를 이용해 `axios`를 사용해 서버에 전송합니다.   

```js
    let body = {
        category: category,
        title: title,
        content: content,
        image: image,
        uid: user.uid,
    }
```   

작성된 게시글들은 PostList 페이지에서 마찬가지로 `axios`를 이용해 데이터를 서버에   
전송하고, 처리합니다.   

```js
    // client
    axios.post("/api/post/list", body)
        .then((response) => {
            if (response.data.success) {
                setPostList([...response.data.postList]);
            }
        })
        .catch((err) => {
            console.log(err);
        });

    // server
    router.post("/list", (req, res) => {
    const { category, searchTerm } = req.body;

    let query = {};

    if (category) {
        query = { category: category }
    } else {
        query = {};
    }

    Post
        .find({
            ...query,
            $or: [
                { title: { $regex: searchTerm } },
                { content: { $regex: searchTerm } }
            ]
        })
        .sort({ _id: -1 })
        .populate("author")
        .exec()
        .then((result) => {
            res.status(200).json({ success: true, postList: result })
        })
        .catch((err) => {
            console.log(err)
            res.status(400).json({ success: false });
        })
})
```   

삭제 및 수정은 글쓰기와 동일한 방식으로 작업합니다.   

```js
    axios
        .post('/api/post/delete', body)
        .then((resonpse) => {
            if (resonpse.data.success) {
                alert('게시글이 삭제되었습니다.')
                navigate('/community')
            }
        });
        .catch((err) => {
            console.log(err);
            alert('게시글 삭제가 실패했습니다.')
        });
```   
   

## 😱트러블 슈팅
```js
npm ERR! code ECONNREFUSED
npm ERR! errno ECONNREFUSED
npm ERR! FetchError: request to http://localhost:3001/ fail
npm ERR!     at ClientRequest.<anonymous> (C:\Users\line\Apde_modules\minipass-fetch\lib\index.js:130:14)
npm ERR!     at ClientRequest.emit (node:events:514:28)
npm ERR!     at _destroy (node:_http_client:875:13)
npm ERR!     at onSocketNT (node:_http_client:895:5)
npm ERR!     at process.processTicksAndRejections (node:int
npm ERR!  FetchError: request to http://localhost:3001/ fai
\node_modules\minipass-fetch\lib\index.js:130:14)
npm ERR!     at ClientRequest.emit (node:events:514:28)
npm ERR!     at _destroy (node:_http_client:875:13)
npm ERR!     at onSocketNT (node:_http_client:895:5)
npm ERR!     at process.processTicksAndRejections (node:internal/process/task_queues:83:21) {
npm ERR!   code: 'ECONNREFUSED',
npm ERR!   errno: 'ECONNREFUSED',
npm ERR!   type: 'system',
npm ERR!   requiredBy: '.'
npm ERR! }
npm ERR!
npm ERR! If you are behind a proxy, please make sure that the
npm ERR! 'proxy' config is set properly.  See: 'npm help config'

npm ERR! A complete log of this run can be found in: C:\Users\line\AppData\Local\np
```

## 📎사이트
test

## 📕스택

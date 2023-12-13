## 클라이언트(Client)
npx create-react-app . 
: 현재 디렉토리에 React 앱을 생성합니다.
npm install react-bootstrap bootstrap 
: React에서 사용할 수 있는 Bootstrap 패키지를 설치합니다.
npm install react-router-dom 
: React 앱에서 라우팅을 관리하기 위한 패키지를 설치합니다.
npm install axios 
: 서버와 HTTP 통신을 하기 위한 라이브러리를 설치합니다.
npm install http-proxy-middleware 
: 개발 시에 CORS 문제를 방지하기 위해 프록시 설정을 도와주는 미들웨어를 설치합니다.
npm install @emotion/css, @emotion/react, @emotion/styled 
: CSS-in-JS 라이브러리인 Emotion 패키지를 설치합니다.
npm install sass

## 서버(Server)
npm init -y 
: 현재 디렉토리에 Node.js 프로젝트를 초기화합니다.
npm install express --save 
: Node.js에서 웹 서버를 구축하기 위한 Express 패키지를 설치합니다.
npm install nodemon --save 
: 개발 시에 파일 변경을 감지하고 서버를 자동으로 재시작해주는 Nodemon 패키지를 설치합니다.
npm install path --save 
: Node.js 내장 모듈인 path를 사용하여 파일 경로를 쉽게 다룰 수 있게 합니다.
npm install mongoose --save 
: MongoDB 데이터베이스와 연동하기 위한 Mongoose 패키지를 설치합니다.MongoDB
MongoDB Atlas를 사용하여 클라우드에 MongoDB를 호스팅합니다. 본인의 계정으로 로그인하고 새 클러스터를 생성합니다.
npm install multer --save
npm install firebase

## Express 앱 구축
Express 앱을 구축하고, 루트 경로에 대한 GET 요청에 "Hello World"를 응답하는 기본 서버를 설정합니다.

## MongoDB 스키마 생성
Mongoose를 사용하여 MongoDB 데이터베이스에 저장할 'Post' 모델을 정의합니다. postSchema에는 post의 'name'과 'content' 필드를 정의합니다.

## Proxy 설정
개발 환경에서 클라이언트와 서버가 다른 포트에서 실행될 때 발생할 수 있는 CORS 문제를 해결하기 위해 프록시 설정을 합니다. 클라이언트에서 '/api'로 시작하는 요청은 'http://localhost:5050'으로 전달됩니다. 이 설정은 클라이언트의 src 폴더에 setupProxy.js 파일을 생성하여 적용합니다.



## client
```
npx create-react-app .  
npm install react-bootstrap bootstrap
npm install react-router-dom   
npm install axios  
npm install http-proxy-middleware  
npm install @emotion/css
npm install @emotion/react
npm install @emotion/styled
```
## server
```
npm init -y;  
npm install express --save;  
npm install nodemon --save; 
npm install path --save;  
npm install mongoose --save;  
```

## monggodb
mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority  


#### 터미널로 파일생성
echo "" > readme.md

#### 제작과정

```js
const express = require("express");
const app = express();
const port = 5050;

app.listen(port, () => {
    console.log("running --> " + port);
})

app.get("/", (req, res) => {
    res.send("Hello World")
})
```
## 서버 세팅

package.json 
```
test-> "start": "nodemon index.js"  
```

## http-proxy-middleware


미들 웨어..?

## </React.StrictMode>


## LF
git config --global core.autocrlf true



## __dirname

require
static


## 리액트 

https://cloud.mongodb.com
https://mongoosejs.com/


https://react-bootstrap.netlify.app 부트스트랩 react
https://emotion.sh  
https://tailwindcss.com/


https://axios-http.com/kr/docs/intro


app.use(express.static(path.join(__dirname, "../client/build/")));
app.use(express.json());
app.use(express.urlencoded({ extended: true }));



## MongoDB post 스키마 생성
```
const mongoose = require("mongoose");

const postSchema = new mongoose.Schema({
    name: String,
    content: String
})

const Post = mongoose.model("Post", postSchema);

module.exports = { Post };
```
- Mongoose를 사용하여 MongoDB 데이터베이스에 저장할 'Post'라는 이름의 모델을 정의하는 코드입니다.

- Mongoose는 MongoDB와 Node.js 사이의 객체 데이터 모델링(ODM) 라이브러리입니다. 이 라이브러리를 사용하면 MongoDB 데이터베이스에 저장할 - 데이터의 구조를 스키마로 정의하고, 이 스키마에 기반한 모델을 만들어 데이터베이스와의 상호작용을 쉽게 할 수 있습니다.

## 글 작성하기

https://reactrouter.com/en/main/hooks/use-navigate##usenavigate


## axios  
요청 req

## proxy 설정
루트 src폴더에 setupProxy 
middleware
"http-proxy-middleware": "^2.0.6", 설치 확인
```
const { createProxyMiddleware } = require('http-proxy-middleware');

module.exports = function (app) {
    app.use(
        '/api',
        createProxyMiddleware({
            target: 'http://localhost:5050',
            changeOrigin: true,
        })
    );
};
```
## 서버 index.js 기본 설정
```
const express = require('express')
const path = require("path")
const mongoose = require("mongoose")

const app = express();
const port = 5050;

app.use(express.static(path.join(__dirname, "../client/build")))

app.listen(port, () => {
    mongoose.connect(
        "mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority"
    )
        .then(() => {
            console.log("connect --> " + port);
        })
        .catch((err) => {
            console.log(err)
        })
})
```
## react build 파일을 경로로 지정
```
const path = require("path"); 

app.get("/", (req, res) => {
    res.sendFile(path.join(__dirname), "../client/build/index.html")
})

app.get("*", (req, res) => {
    res.sendFile(path.join(__dirname), "../client/build/index.html")
})
```
## monmgoose 연결
```
const mongoose = require("mongoose");


mongoose.connect(
    "mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority"
)
    .then(() => {
        console.log("listening --> " + port);
        console.log("mongoose --> connecting");
    })
    .catch((err) => {
        console.log(err)
    })
```
## 서버로 요청
```
  axios.post("/api/test")
            .then((response) => {
                alert("요청 성공");
                console.log(response);
                setText(response.data.text);
            })
            .catch((err) => {
                alert("요청 실패");
                console.log(err)
            })
    }, [])
```
## 서버에서 요청 받고 보내줌
```
app.post("/api/test", (req, res) => {
    console.log(req);
    res.status(200).json({ success: true, text: "안녕하세요!" });
})
```


## 클라이언트에서 body[] 전송 
server index.js
body path 추가해야됨
```
app.use(express.json());
app.use(express.urlencoded({ extended: true }));
```


## 스키마 생성
```
const mongoose = require("mongoose");

const postSchema = new mongoose.Schema({
    name: String,
    content: String
}, { collection: "posts" })

const Post = mongoose.model("Post", postSchema);

module.exports = { Post };
```

## 스키마 생성, 데이터베이스에 데이터 저장
```
const { Post } = require("./Model/Post.js");


app.post("/api/test", (req, res) => {
    const BlogPost = new Post({ title: "안녕하세요", content: "내용입니다." })
    BlogPost.save().then(() => {
        res.status(200).json({ success: true });
    })
})

```

## 클라이언트 데이터 보내기
버튼 눌렀을떄 title content 보내기
```
const onSubmit = (e) => {
        e.preventDefault();

        if (title === "" || content === "") {
            return alert("내용을 채워주세요!")
        }
        let body = {
            title: title,
            content: content
        }
        axios
            .post("/api/post/submit", body)
            .then((res) => {
                if (Response.data.success) {
                    alert("글 작성이 완료되었습니다.");
                } else {
                    alert("글 작성이 실패하였습니다.")
                }
            })
    }
```

## 서버 데이터 받기 dm저장
```
app.post("/api/post/submit", (req, res) => {
    let temp = req.body;
    console.log(temp)


    const BlogPost = new Post(temp)
    BlogPost.save()
        .then(() => {
            res.status(200).json({ success: true });
        })
        .catch((err) => {
            res.status(400).json({ success: false })
        })
})
```

## LIST


클라이언트  

요청 성공시 포스트 리스트 받음
```
    const [postList, setPostList] = useState([]);

    useEffect(() => {
        axios.post("/api/post/list")
            .then((response) => {
                if (response.data.success) {
                    setPostList([...response.data.postList]);
                }
            })
            .catch((err) => {
                console.log(err)
            })
    }, [])
```


서버  

요청받으면 경로에 대한 post요청을 처리,
콜백함수 실행
.then((doc) => {...}) : find().exec()에서 반환받은 Promise가 resolve(성공) 되면 실행되는 콜백 함수
찾아낸 문서들이 doc에 담겨서 전달
이 콜백 함수 내부에서는 res.status(200).json({ success: true, postList: doc })를 통해 HTTP 상태 코드 200과 함께 성공 메시지와 찾아낸 문서들을 JSON 형태로 응답
```
app.post("/api/post/list", (req, res) => {
    Post.find().exec()
        .then((doc) => {
            res.status(200).json({ success: true, postList: doc })
        })
        .catch((err) => {
            console.log(err)
            res.status(400).json({ success: false })

        })
})
```
find 찾기
exec 실행
찾아서 실행



## 게시물 PostNum 생성시키기
-번호 1씩 증가시켜서 저장 (게시글 수정, 삭제시 필요함)

### 1. Counter 스키마 생성
```
const mongoose = require("mongoose");

const counterSchema = new mongoose.Schema({
    name: String,
    postNum: Number
}, { collection: "counter" })

const Counter = mongoose.model("Counter", counterSchema);

module.exports = { Counter };
```
```
const { Counter } = require("./Model/Counter.js");
```
### 2. 번호 1씩 증가시켜서 저장
-{ $inc: { postNum: 1 } } 증가시키기
```
app.post("/api/post/submit", (req, res) => {
    let temp = req.body;
    // 넘버 추가 작업 (글 삭제,수정하기위해)
    Counter.findOne({ name: "counter" })
        .exec()
        .then((counter) => {
            temp.postNum = counter.postNum;

            const BlogPost = new Post(temp);

            BlogPost.save()
                .then(() => {
                    // 번호를 1씩 증가
                    Counter.updateOne({ name: "counter" }, { $inc: { postNum: 1 } })
                        .then(() => {
                            res.status(200).json({ success: true });
                        })
                })

        })
        .catch((err) => {
            console.log(err)
            res.status(400).json({ success: false })
        })



    const BlogPost = new Post(temp)
    BlogPost.save()
        .then(() => {
            res.status(200).json({ success: true });
        })
        .catch((err) => {
            console.log(err)
            res.status(400).json({ success: false })
        })
})
```




# 작업순서

## client
```
npx create-react-app .  
npm install react-bootstrap bootstrap
npm install react-router-dom   
npm install axios  
npm install http-proxy-middleware  
npm install @emotion/css
npm install @emotion/react
npm install @emotion/styled
```
## server
```
npm init -y;  
npm install express --save;  
npm install nodemon --save; 
npm install path --save;  
npm install mongoose --save;  
```

- server에 index.js 생성 -> packge.json "start": "nodemon index.js"

- express

- npm run build

- 몽구스 연결

```
const express = require('express');
const app = express();
const port = 5050;
const path = require("path");
const mongoose = require("mongoose");
```
- express 모듈을 가져와서 express 객체를 생성합니다.
- 5050 포트를 사용할 수 있는 app 객체를 생성합니다.
- path 모듈을 가져옵니다.
- mongoose 모듈을 가져옵니다.

## 미들웨어
```
app.use(express.static(path.join(__dirname, "../client/build")));
```
- express.static 미들웨어를 사용하여 정적 파일을 제공합니다.
- __dirname은 현재 실행 중인 스크립트의 디렉토리 경로를 나타냅니다.
- ../client/build 경로에 있는 정적 파일들을 제공합니다.

## 데이터베이스 연결
```
mongoose.connect(
    "mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority"
)
    .then(() => {
        console.log("listening --> " + port);
        console.log("mongoose --> connecting");
    })
    .catch((err) => {
        console.log(err);
    });
```
- mongoose.connect를 사용하여 MongoDB 데이터베이스에 연결합니다.
- 연결이 성공하면 then 블록이 실행되고, 포트 번호와 "mongoose --> connecting" 메시지가 출력됩니다.
- 연결이 실패하면 catch 블록이 실행되고, 오류 메시지가 출력됩니다.

## 리스닝 
```
app.listen(port, () => {
    console.log("listening --> " + port);
});
```
- app 객체를 port 번호로 리스닝하여 서버를 실행합니다.
서버 실행 후 "listening --> 포트번호" 메시지가 -출력됩니다.

## ㅇㅇ
```
app.get("/", (req, res) => {
    res.sendFile(path.join(__dirname, "../client/build/index.html"));
});

app.get("*", (req, res) => {
    res.sendFile(path.join(__dirname, "../client/build/index.html"));
});
```
- 루트 경로("/")로 접속했을 때와 그 외의 모든 경로("*")로 접속했을 때에 대해 같은 HTML 파일(../client/build/index.html)을 전송합니다.
- 클라이언트가 요청한 경로에 관계없이 항상 같은 HTML 파일을 전송합니다.

## axios
```
app.post("/api/test", (req, res) => {
    console.log(req);
    res.status(200).json({ success: true });
});
```
- 클라이언트가 /api/test 경로로 POST 요청을 보낼 때, 요청 객체(req)를 콘솔에 출력하고, 성공 상태(200)와 JSON 응답 { success: true }을 전송합니다.
- 이렇게 코드가 동작하여 Express 서버를 생성하고, 정적 파일을 제공하며, MongoDB에 연결하고, 라우팅을 설정하고, API 요청을 처리합니다.

## 요청 -> body값 전달
```
app.use(express.json()); 
app.use(express.urlencoded({ extended: true })); 

app.post("/api/test", (req, res) => {
    console.log(req.body);
    res.status(200).json({ success: true })
})
```

## post스키마 생성
```
const mongoose = require("mongoose");

const postSchema = new mongoose.Schema({
    title: String,
    content: String,
    postNum: Number
}, { collection: "posts" })

```
### Post.js
collection : 스키마 이름

이 코드는 Mongoose를 사용하여 MongoDB 데이터베이스와 상호작용하는 JavaScript 노드 모듈입니다. 각 줄에 대한 해석은 다음과 같습니다.

const mongoose = require("mongoose");
'mongoose'라는 이름의 노드 모듈을 불러옵니다. Mongoose는 MongoDB 객체 데이터 모델링을 위한 라이브러리입니다.
const postSchema = new mongoose.Schema({ ... }, { collection: "posts" })
'postSchema'라는 새로운 Mongoose 스키마를 생성합니다. 이 스키마는 'title'과 'content'라는 두 개의 필드를 가진 객체로 정의되어 있습니다. 각 필드의 데이터 타입은 String입니다. 스키마 옵션으로 'posts'라는 컬렉션을 사용하도록 설정하였습니다.
const Post = mongoose.model("Post", postSchema);
'Post'라는 이름의 Mongoose 모델을 생성합니다. 이 모델은 이전에 생성한 'postSchema'를 사용합니다. 이 모델을 통해 'posts' 컬렉션에 있는 데이터를 조회, 생성, 수정, 삭제하는 등의 작업을 수행할 수 있습니다.
module.exports = { Post };
이 모듈에서 생성한 'Post' 모델을 외부로 내보냅니다. 이렇게 하면 이 모듈을 불러온 다른 파일에서 'Post' 모델을 사용할 수 있게 됩니다.
참고로, 주석 처리된 // postNum: Number 부분을 보면, 원래 'postNum'이라는 필드도 스키마에 포함되었을 것으로 추측할 수 있습니다. 이 필드는 현재 주석 처리되어 사용되지 않고 있습니다.

```
const Post = mongoose.model("Post", postSchema);

module.exports = { Post };
```
```
app.post("/api/test", (req, res) => {
    const BlogPosts = new Post({ title: "타이틀", content: "내용" })
    BlogPosts.save().then(() => {
        res.status(200).json({ success: true, text: "안녕" });
    })
}) 
```
## 게시물 저장
```
app.post("/api/post/submit", (req, res) => {
    let temp = req.body;
    console.log(temp);

    const BlogPosts = new Post(temp)
    BlogPosts.save().then(() => {
        res.status(200).json({ success: true });
    })
        .catch((err) => {
            console.log(err)
        })
})

```
## db에 있는 데이터 보내기
```
app.post("/api/post/list", (req, res) => {
    Post.find().exec()
        .then((doc) => {
            res.status(200).json({ success: true, postList: doc })
        })
        .catch((err) => {
            console.log(err)
            res.status(400).json({ success: false })
        })
})
```
- /api/post/list 경로로 POST 요청이 들어왔을 때, 콜백 함수가 실행됩니다.
- Post.find().exec()를 호출하여 모든 블로그 포스트를 조회합니다.
- 조회 결과는 doc 변수에 저장됩니다.
- 조회가 성공하면 then 블록이 실행되고, 응답 객체(res)에 HTTP 상태 코드 200과 JSON 응답 { success: true, postList: doc }을 전송합니다. postList에는 조회된 블로그 포스트들이 포함됩니다.
- 조회가 실패하면 catch 블록이 실행되고, 오류 메시지를 콘솔에 출력하고, 응답 객체(res)에 HTTP 상태 코드 400과 JSON 응답 { success: false }을 전송합니다.

## 게시물 고유번호 생성

1. countNum 스키마 생성
```
const mongoose = require("mongoose");

const postSchema = new mongoose.Schema({
    title: String,
    content: String,
    postNum: Number
}, { collection: "posts" })

const Post = mongoose.model("Post", postSchema);

module.exports = { Post };
```

2. postNum 값 생성
```
app.post("/api/post/submit", (req, res) => {
    let temp = req.body;
    Counter.findOne({ name: "counter" }).exec()
        .then((counter) => {
            temp.postNum = counter.postNum;

            const BlogPosts = new Post(temp);

            BlogPosts.save().then(() => {
                Counter.updateOne({ name: "counter" }, { $inc: { postNum: 1 } })
                    .then(() => {
                        res.status(200).json({ success: true });
                    })
            })

        })
        .catch((err) => {
            console.log(err);
            res.status(400).json({ success: false })
        })

})
```
- /api/post/submit 경로로 POST 요청이 들어왔을 때, 콜백 함수가 실행됩니다.
- let temp = req.body;를 통해 요청 본문의 데이터를 temp 변수에 저장합니다.
- Counter.findOne({ name: "counter" }).exec()를 호출하여 "counter" 이름을 가진 카운터를 조회합니다.
- 조회 결과는 counter 변수에 저장됩니다.
- temp.postNum = counter.postNum;를 통해 temp 객체의 postNum 필드에 조회한 카운터의 postNum 값을 할당합니다.
- const BlogPosts = new Post(temp);를 통해 temp 객체를 사용하여 새로운 블로그 포스트를 생성합니다.
- BlogPosts.save().then(() => { ... })를 호출하여 새로운 블로그 포스트를 MongoDB에 저장합니다.
- 저장이 완료되면 then 블록이 실행되고, Counter.updateOne({ name: "counter" }, { $inc: { postNum: 1 } })를 호출하여 카운터의 postNum 값을 1 증가시킵니다.
- 카운터 업데이트가 완료되면 then 블록이 실행되고, 응답 객체(res)에 HTTP 상태 코드 200과 JSON 응답 { success: true }을 전송합니다.
- 조회나 저장, 업데이트 과정에서 오류가 발생하면 catch 블록이 실행되고, 오류 메시지를 콘솔에 출력하고, 응답 객체(res)에 HTTP 상태 코드 400과 JSON 응답 { success: false }을 전송합니다.


따라서, /api/post/submit 경로로 POST 요청을 보내면 요청 본문의 데이터를 사용하여 새로운 블로그 포스트를 생성하고, 해당 포스트가 MongoDB에 저장됩니다. 또한, 카운터의 postNum 값도 증가시켜서 다음 포스트의 번호를 유지합니다. 응답에는 success 값이 true로 설정되어 성공 여부를 나타냅니다. 오류가 발생한 경우에는 success 값이 false로 설정되고, 오류 메시지가 콘솔에 출력됩니다.


## 게시물 보기 
1. App.js detail components 추가
```
<Route path='/post/:postNum' element={<Detail />}></Route>
```
- path 설정
- <Route> 컴포넌트를 사용하여 경로에 대한 라우팅을 설정합니다.
path='/post/:postNum'은 /post/ 다음에 변수 postNum이 오는 경로를 의미합니다. :를 사용하여 동적인 경로를 나타냅니다.
element={<Detail />}은 해당 경로에 매칭되었을 때, 렌더링할 컴포넌트를 지정합니다. <Detail /> 컴포넌트가 렌더링됩니다.
따라서, /post/ 다음에 오는 postNum 값에 따라 <Detail /> 컴포넌트가 렌더링되는 라우팅 설정입니다. 예를 들어, /post/1 경로에 접속하면 <Detail /> 컴포넌트가 렌더링됩니다. postNum은 동적으로 변할 수 있으므로, 해당 값을 <Detail /> 컴포넌트에서 사용하여 필요한 작업을 수행할 수 있습니다.
```
app.post("/api/post/detail", (req, res) => {
    Post.findOne({ postNum: req.body.postNum })
        .exec()
        .then((doc) => {
            console.log(doc);
            res.status(200).json({ success: true, post: doc });
        })
        .catch((err) => {
            res.status(400).json({ success: false });
        });
});
```
- Post.findOne({ postNum: req.body.postNum })를 호출하여 postNum 필드가 요청 본문의 postNum 값과 일치하는 포스트를 조회합니다.
- 조회 결과는 doc 변수에 저장됩니다
- 조회가 성공하면 then 블록이 실행되고, 조회된 포스트 정보가 콘솔에 출력되고, 응답 객체(res)에 HTTP 상태 코드 200과 JSON 응답 { success: true, post: doc }을 전송합니다. post에는 조회된 포스트의 상세 정보가 포함됩니다.
- 조회가 실패하면 catch 블록이 실행되고, 응답 객체(res)에 HTTP 상태 코드 400과 JSON 응답 { success: false }을 전송합니다.
## 글 삭제
```


```

## 글 수정
```
app.post("/api/post/edit", (req, res) => {
    let temp = {
        title: req.body.title,
        content: req.body.content
    }
    Post.updateOne({ postNum: Number(req.body.postNum) }, { $set: temp })
        .exec()
        .then(() => {
            res.status(200).json({ success: true })
        })
        .catch((err) => {
            res.status(400).json({ success: false })
            console.log(err)
        })
})
```
이 코드는 Express.js를 사용해서 HTTP POST 요청을 처리하는 라우터입니다. "/api/post/edit" 경로로 POST 요청이 들어오면, 이 요청을 처리하기 위한 함수가 실행됩니다.

요청의 본문(req.body)에는 'title', 'content', 'postNum'이라는 키를 가진 객체가 포함되어 있어야 합니다. 이 정보는 클라이언트에서 보낸 데이터입니다.
```
let temp = {
    title: req.body.title,
    content: req.body.content
}
```
위의 코드에서는 요청 본문에서 'title'과 'content' 값을 가져와서 새로운 'temp' 객체를 생성합니다.
```
Post.updateOne({ postNum: Number(req.body.postNum) }, { $set: temp })
```
그 다음에는 Post.updateOne() 함수를 호출하여 데이터베이스에서 하나의 문서를 업데이트합니다. 이 함수는 첫 번째 인자로 주어진 조건에 맞는 문서를 찾아서, 두 번째 인자로 주어진 변경사항을 적용합니다. 여기서는 postNum이 req.body.postNum과 일치하는 문서를 찾아서, 해당 문서의 'title'과 'content' 값을 'temp' 객체의 값으로 변경합니다.
```
.exec()
.then(() => {
    res.status(200).json({ success: true })
})
.catch((err) => {
    res.status(400).json({ success: false })
    console.log(err)
})
```
마지막으로, exec() 함수를 호출하여 데이터베이스 쿼리를 실행합니다. 쿼리가 성공적으로 완료되면, HTTP 상태 코드 200과 함께 { success: true }를 응답 본문으로 보냅니다. 만약 쿼리 실행 중에 오류가 발생하면, HTTP 상태 코드 400과 함께 { success: false }를 응답 본문으로 보내고, 오류 내용을 콘솔에 출력합니다.

이 코드는 일반적으로 게시글을 수정하는 API에서 사용될 수 있습니다. 클라이언트에서 수정하려는 게시글의 번호와 새로운 제목, 내용을 서버에 보내면, 서버는 이 정보를 사용해서 데이터베이스에 저장된 해당 게시글을 업데이트합니다.

## express.Router

express.Router 클래스를 사용하면 모듈식 마운팅 가능한 핸들러를 작성할 수 있습니다. Router 인스턴스는 완전한 미들웨어이자 라우팅 시스템이며, 따라서 “미니 앱(mini-app)”이라고 불리는 경우가 많습니다.

다음 예에서는 라우터를 모듈로서 작성하고, 라우터 모듈에서 미들웨어 함수를 로드하고, 몇몇 라우트를 정의하고, 기본 앱의 한 경로에 라우터 모듈을 마운트합니다.

다음의 내용이 입력된 birds.js라는 이름의 라우터 파일을 앱 디렉토리에 작성하십시오.
```
var express = require('express');
var router = express.Router();

// middleware that is specific to this router
router.use(function timeLog(req, res, next) {
  console.log('Time: ', Date.now());
  next();
});
// define the home page route
router.get('/', function(req, res) {
  res.send('Birds home page');
});
// define the about route
router.get('/about', function(req, res) {
  res.send('About birds');
});

module.exports = router;
```

```
var birds = require('./birds');
...
app.use('/birds', birds);
```



## multer 이미지 올리기
```
const multer = require("multer");


const storage = multer.diskStorage({
    destination: function (req, file, cb) {
        cb(null, 'image/')
    },
    filename: function (req, file, cb) {
        cb(null, `${Date.now()}_${file.originalname}`)
    }
})

const upload = multer({ storage: storage }).single("file");

router.post('/image/upload', (req, res) => {
    upload(req, res, (err) => {
        if (err) {
            res.status(400).json({ success: false })
        } else {
            res.status(200).json({ success: true, filePath: res.req.file.path })
        }

    })
})

```


```
<Main>
        <Routes>
          <Route path='/' element={<Home />}></Route>
          <Route path='/write' element={<Write />}></Route>
          <Route path='/list' element={<List />}></Route>
          <Route path='/detail/:postNum' element={<Detail />}></Route>
          <Route path='/modify/:postNum' element={<Modify />}></Route>
        </Routes>
      </Main>
import React from 'react'

const Main = (props) => {
    return (
        <main id='main' role='main'>
            {props.children}
        </main>
    )
}

export default Main

```
Main 컴포넌트에서 자식 컴포넌트가 보여지는 방식
Main 컴포넌트는 React Router v6의 Routes 컴포넌트를 사용하여 자식 컴포넌트를 렌더링합니다. Routes 컴포넌트는 path prop을 사용하여 URL 경로와 컴포넌트를 매핑하고, URL 경로가 일치할 때 해당 컴포넌트를 렌더링합니다.

구체적인 동작 방식은 다음과 같습니다:

브라우저에서 URL 경로 변경: 사용자가 브라우저에서 URL 경로를 변경하면, React Router는 새로운 URL을 검사합니다.
Routes 컴포넌트에서 매핑된 경로 확인: Routes 컴포넌트는 정의된 경로 목록을 검토하여 변경된 URL과 일치하는 경로를 찾습니다.
일치하는 경로에 매핑된 컴포넌트 렌더링: 일치하는 경로가 발견되면, Routes 컴포넌트는 해당 경로에 매핑된 컴포넌트를 렌더링합니다.
Main 컴포넌트에서 자식으로 전달: 렌더링된 컴포넌트는 Main 컴포넌트의 children prop을 통해 Main 컴포넌트 내부에 표시됩니다.
예시:

/ 경로로 이동하면 <Home /> 컴포넌트가 렌더링됩니다.
/write 경로로 이동하면 <Write /> 컴포넌트가 렌더링됩니다.
/list 경로로 이동하면 <List /> 컴포넌트가 렌더링됩니다.
/detail/123 경로로 이동하면 <Detail /> 컴포넌트가 렌더링되고, URL 파라미터 postNum은 123 값으로 컴포넌트에 전달됩니다.
/modify/456 경로로 이동하면 <Modify /> 컴포넌트가 렌더링되고, URL 파라미터 postNum은 456 값으로 컴포넌트에 전달됩니다.
요약:

React Router v6의 Routes 컴포넌트는 URL 경로와 컴포넌트를 매핑합니다.
URL 경로가 변경되면 Routes 컴포넌트는 일치하는 경로를 찾고 해당 컴포넌트를 렌더링합니다.
렌더링된 컴포넌트는 Main 컴포넌트의 children prop을 통해 Main 컴포넌트에 표시됩니다.


# client 
1. 설치
2. react 폴더정리


# server
1. 설치
2. index.js 생성
3. pakage.json > "start": "nodemon index.js"
4. express
5. port 5050
6. mongoose 연결
mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority
```
const express = require("express");
const path = require("path");
const mongoose = require("mongoose");

const app = express();
const port = 5050;

app.use(express.static(path.join(__dirname, "../client/build")));
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

app.listen(port, () => {
    mongoose.connect(
        "mongodb+srv://hoho:dlwm5656@cluster0.ctgdo3h.mongodb.net/?retryWrites=true&w=majority"
    )
        .then(() => {
            console.log("listening  --> " + port);
            console.log("mongoose --> connecting");
        })
        .catch((err) => {
            console.log(err)
        })
})

app.get("/", (req, res) => {
    res.sendFile(path.join(__dirname, "../client/build/index.html"));
})
app.get("*", (req, res) => {
    res.sendFile(path.join(__dirname, "../client/build/index.html"));
});
```


# firebase 
로그인 
프로젝트 만들기 


## 경고
One of your dependencies, babel-preset-react-app, is importing the
"@babel/plugin-proposal-private-property-in-object" package without
declaring it in its dependencies. This is currently working because
"@babel/plugin-proposal-private-property-in-object" is already in your
node_modules folder for unrelated reasons, but it may break at any time.

babel-preset-react-app is part of the create-react-app project, which
is not maintianed anymore. It is thus unlikely that this bug will
ever be fixed. Add "@babel/plugin-proposal-private-property-in-object" to
your devDependencies to work around this error. This will make this message
go away.

babel-preset-react-app이 "@babel/plugin-proposal-private-property-in-object" 패키지를 사용하고 있지만, 그 자체의 의존성에서는 이를 선언하지 않았다는 것을 알려줍니다. 이러한 문제는 패키지 관리자가 패키지의 의존성을 올바르게 관리하지 않았을 때 발생합니다.

이 문제를 해결하려면, 권장하는 방법대로 개발 의존성에 "@babel/plugin-proposal-private-property-in-object" 패키지를 추가하면 됩니다. 다음과 같이 명령어를 실행하면 됩니다.


npm install --save-dev @babel/plugin-proposal-private-property-in-object
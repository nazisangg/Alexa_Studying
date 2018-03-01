#### 类似alexa
- Automation system
  - roseberry pie
  - build a web app so that you can control it from distance
  - wise control(the system is actually on cloud)
  - add a “home addmission system” 达成wireless control
  - build own custom skills

#### language  
- node js and python（AWS lamda and web service）

#### otherskills
- AWS DynamoDB
- AWS CLI
- OAuth
- GIT
- Heroku
- Coding guidelines
- free echo simulator

#### components
- Amazon Echo
  - small speaker,control by your voice, connected to
  - connected to  AWS base service called Alexa
  - default word alexa。剩下的可以用weak word。
  - echo Dot (cheaper and samller version) 区别就在speaker上面
  - can be connected to any other hardware（例如roseberry pie）

- build in features：
  - how is the weather
  - set my alarm for 1 hour
  - whats in the news
  - IFTTT(就是给你的手机打个电话)
  - find me nearby thai restaurant
  - tell me about the movie <title>
  - smart home
    - wemo
    - philips hue
    - samsung smarthings
    - wink
    - nest and many more
- online test website
  - echosim.io
  - hold the button and speak
[alexa user guide](https://www.amazon.com/b/ref=ech_dp_pack?node=16067214011)
- Alexa Voice Service（AVS）
- Alexa Skill kit（ASk ）
  - build own skills with alexa skill kit
  -  shi1 self-service APIs, tools, documentation and code samples
  - 这令在alexa 上增加custom skill 变得简单。
- default


#### AWS Lambda Function
- skill goal and setup
- request generation
- AWS lambda function setup
- local environment， AWS CLI，automation.
- more functions:
  - APIs
  - SSML
  - sessions and build-in intents
  - including card
- debugging
- testing using mocha framework

#### Greeting skill using Web service as endpoint
```
Goal：wishing our guest
    should say morning/afternoon/evening + {name}
invocation:
          name: "greeter" // 调用的skill的名字
          // 用户可以说open greeter然后功能就开始了
          Open/launch/talk to/ begin greeter// 这个是不加command的调用方法
          tell/ask greeter to/for/about <some request> 这个是加command的方法

所以一个比较formal的request可以是：

        Alexa，ask “greeter” to “say hello to <guest name>”

也就是说我们要让Alexa能够用多种方式接受问题并正确返回。（叫做 wise instruction model）这个东西可以拿过来convey request

然后返回的时候是：Response ： Hello <guest>, Good Morning/Afternoon/Evening

```

```
开始一个new skills：
进入 alexa develop portal -> Alexa -> Skill information -> 增加一个 Name： Greetings -> greeter -> save -> next ->  // 这个是set 所有的name以及上面的invocation的setup

更改 Sample Utterances：其实就是问alexa的话.

HelloIntent say hello to {FirstName}
// 不同的 utterance
HelloIntent wish hello to {FirstName}
HelloIntent greet guest {FirstName}
HelloIntent greet {FirstName}

// there are rules for sample Utterances


{
  "intents": [
    {
      "intent": "HelloIntent",
      "slots":[
        {
          "name": "FirstName",
          "type": "GUEST_NAMES"//这个是看输出输入的type是什么，例如AMAZON.FOUR_DIGIT_NUMBER这种
                    //比如 AMAZON.Actor 就包含了所有的actor/actress的名字
                    // 当然了也可以自己建立自己的slot type

        }
      ]
    }
    ]
}

更改 Intent Schema 其实是个json format的东西

```

- introduction
  - there are rules for sample Utterances
    - numbers 应该是words而不是数字
    - DJ 应该是d. j. 而不是DJ
    - {} 这个是variables的
  - Alexa Request to endpoint 的过程：
    - 从aws echo 端接受request ，音频发到amazon alexa service，在这里进行voice recognition 并且decode command，他会尽量的去match invocation name -> 在developer protal的 时候 invocation name/app_id 之类的会在developer protal里面搜索，假如match了，剩下的会被decode成一个request
    - lamda function 会拿这个request然后返回一个response。

- coding (python and Flask web framework)
- deploying lical web server
- hosting the skill on Heroku
- testing using python unittest
- requirement of web service and flask-ask (security problem)
- Greeting skill using flask-ask and deploying to Heroku


#### Food Nutrition lookup skill development(more realtime practice application)

- introduction

- setup

- coding testing and deploying

- pubulishing process

- certification requirement and fix

- improvement

#### Email checker skill account linking feature

- account lining introduction

- Gmail APIs and google API console setup

- skill setuo

- coding testing and deploying

- voice password and AWS DynamoDB setup

- adding Forget Pin functionality

- conclusion

<template>
  <div class="hello" >
    <div :class="defaultHeadClass">
      <b-navbar class="pl-5 pr-5" toggleable="md">
        <b-navbar-brand>buluoge</b-navbar-brand>
        <!--界面过小时，用于展开更多按钮-->
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <!-- target 对应的是id -->
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item class="mr-2" @click="whereGo('feedback')">你提我改</b-nav-item>
            <b-nav-item class="mr-2" @click="whereGo('feedback')">留言墙</b-nav-item>
            <b-nav-item class="mr-2" @click="whereGo('index')">首页</b-nav-item>
          </b-navbar-nav>

          <!-- <b-navbar-nav v-if="search">
            <c-input class="y-0" v-model="searchKeyWord" type="search" placeholder="请输入搜索关键字..."  append-type="button" append-icon="search" @enter="goSearch(searchKeyWord)" @appendClick="goSearch(searchKeyWord)"></c-input>
          </b-navbar-nav> -->

          <!--用户已登录功能栏-->
          <!-- <b-navbar-nav v-if="$store.getters.openId " class="ml-auto">
            <b-button variant="dark" @click="whereGo('writeArticle')">
              <c-svg-icon icon-class="edit-w" size="1.6em" margin-none />文稿创作
            </b-button> -->

            <!--用户快捷导航-->
            <!-- <b-nav-item-dropdown variant="b-popover-dark">
              <template v-slot:button-content>{{getUserStore('nickname')}}</template>
              <b-dropdown-item @click="whereGo('userInfo',{'openId':getUserStore('openId')})">我的首页</b-dropdown-item>
              <b-dropdown-item @click="whereGo">帮助和反馈</b-dropdown-item>
              <b-dropdown-item @click="logout">退出登录</b-dropdown-item>
            </b-nav-item-dropdown> -->

            <!--用户消息-->
            <!-- <b-nav-item-dropdown text="消息">
              <b-dropdown-item @click="whereGo">
                <b-badge :count="getMessageStore('messageMarkedCount')" />动态信息
              </b-dropdown-item>
              <b-dropdown-item @click="whereGo">
                <b-badge :count="getMessageStore('messageChatCount')" />我的消息
              </b-dropdown-item>
              <b-dropdown-item @click="whereGo">
                <b-badge :count="getMessageStore('messageSystemCount')" />系统消息
              </b-dropdown-item>
            </b-nav-item-dropdown> -->
          <!-- </b-navbar-nav> -->

          <!--未登录功能栏-->
          <!-- v-else  -->
          <b-navbar-nav class="ml-auto">
            <b-button variant="outline-success" class="mx-2" @click="whereGo('register')">注册</b-button>
            <b-button variant="outline-dark" class="mx-2" @click="whereGo('login')">登录</b-button>
          </b-navbar-nav>

        </b-collapse>
      </b-navbar>
    </div>
    <b-container>
      <b-row align-v="center" align-h="center" class="mb-5">
        <b-col cols="12" md="8" order-md="2">
          <div class="home-card-0 rounded-lg"></div>
        </b-col>

        <b-col cols="12" md="4" order-md="1">
          <h3 class="text-sm-center text-md-left text-center">
            Work with any team
          </h3>
          <p class="text-sm-center text-md-left text-center">
            Whether it's for work, a side project or even the next family
            vacation, Trello helps your team stay organized.
          </p>
          <div class="text-sm-center text-md-left text-center">
            <b-button :to="{ name: 'signup' }" href="#" variant="primary">
              <span class="mr-3">Start doing</span>
              <b-icon icon="arrow-right" animation="cylon"></b-icon>
            </b-button>
          </div>
        </b-col>
      </b-row>

      <b-row align-v="center" align-h="center" class="mb-5">
        <b-col cols="6" md="4">
          <div class="home-card-1 rounded-lg"></div>
        </b-col>

        <b-col cols="12" md="8">
          <h3 class="text-sm-center text-md-left text-center">
            Information at a glance
          </h3>
          <p class="text-sm-center text-md-left text-center">
            Dive into the detail by adding comments, attachments, due dates, and
            more directly to Trello cards. Collaborate on projects from
            beginning to end.
          </p>
        </b-col>
      </b-row>

      <b-row align-v="start" align-h="around" class="mb-5">
        <b-col cols="12" md="4" order-md="2">
          <div class="home-card-2 rounded-lg"></div>
        </b-col>

        <b-col cols="12" md="8" order-md="1">
          <h3>
            Built-In Workflow Automation With Butler
          </h3>
          <p class>
            Let the robots do the work! Boost productivity by unleashing the
            power of automation across your entire team with Bulter, and remove
            tedious tasks from your to-do lists with :
          </p>
          <ul>
            <li>Rule-Based Triggers</li>
            <li>Custom Card & Board Buttons</li>
            <li>Calendar Commands</li>
            <li>Due Date Commands</li>
          </ul>
        </b-col>
      </b-row>

      <b-row>
        <b-col>
          <h2 class="text-center">See how it works</h2>
          <p class="text-center">
            Go from idea to action in seconds with Trello's intuitively simple
            boards, lists, and cards.
          </p>
        </b-col>
      </b-row>

      <b-row align-h="around" class="mb-5">
        <b-col cols="12" md="8">
          <b-carousel
            v-model="slide"
            :interval="4000"
            controls
            indicators
            background="#ababab"
            img-width="1024"
            img-height="480"
            style="text-shadow: 1px 1px 2px"
          >
            <b-carousel-slide
              caption="Blank Image"
              img-blank
              img-alt="Blank image"
              v-for="(item,key) in img"
              :key='key'
            >
              <!-- <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Suspendisse eros felis, tincidunt a tincidunt eget, convallis
                vel est. Ut pellentesque ut lacus vel interdum.
              </p> -->
              <p>{{item.value}}</p>
            </b-carousel-slide>
            <!-- <b-carousel-slide
              caption="Blank Image"
              img-blank
              img-alt="Blank image"
            >
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Suspendisse eros felis, tincidunt a tincidunt eget, convallis
                vel est. Ut pellentesque ut lacus vel interdum.
              </p>
            </b-carousel-slide>

            <b-carousel-slide
              caption="Blank Image"
              img-blank
              img-alt="Blank image"
            >
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Suspendisse eros felis, tincidunt a tincidunt eget, convallis
                vel est. Ut pellentesque ut lacus vel interdum.
              </p>
            </b-carousel-slide>

            <b-carousel-slide
              caption="Blank Image"
              img-blank
              img-alt="Blank image"
            >
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Suspendisse eros felis, tincidunt a tincidunt eget, convallis
                vel est. Ut pellentesque ut lacus vel interdum.
              </p>
            </b-carousel-slide>

            <b-carousel-slide
              caption="Blank Image"
              img-blank
              img-alt="Blank image"
            >
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Suspendisse eros felis, tincidunt a tincidunt eget, convallis
                vel est. Ut pellentesque ut lacus vel interdum.
              </p>
            </b-carousel-slide> -->
          </b-carousel>
        </b-col>
      </b-row>

      <b-row align-h="center" class="mb-5">
        <b-col cols="8">
          <h3 class="text-center">Trello your way</h3>
          <p class="text-center">
            User Trello the way your team works best. We've got the flexibility
            & features to fit any team's style.
          </p>
        </b-col>
      </b-row>

      <b-row align-h="center" class="mb-5">
        <b-col cols="12" lg="4">
          <div class="text-center">
            <b-card
              title="The Team Playbook"
              img-src="0.jpg"
              img-alt="Image"
              img-top
              tag="article"
              class="mb-2"
            >
              <b-card-text>
                <p>
                  It's easy to get your team up and running with Trello. We've
                  collected all of the boards and tools you need to succeed in
                  one handy resource
                </p>
              </b-card-text>

              <b-button href="#" variant="primary">Make A Game Plan</b-button>
            </b-card>
          </div>
        </b-col>

        <b-col cols="12" lg="4">
          <div class="text-center">
            <b-card
              title="A Productivity Platform"
              img-src="1.jpg"
              img-alt="Image"
              img-top
              tag="article"
              class="mb-2"
            >
              <b-card-text>
                <p>
                  Integrate the apps your team already uses directly into your
                  workflow. Powers-Ups turn Trello boards into living
                  applications to meet your team's unique business need.
                </p>
              </b-card-text>

              <b-button href="#" variant="primary">
                Power-Up Your Workflow
              </b-button>
            </b-card>
          </div>
        </b-col>

        <b-col cols="12" lg="4">
          <div class="text-center">
            <b-card
              title="Always In Sync"
              img-src="2.jpg"
              img-alt="Image"
              img-top
              tag="article"
              class="mb-2"
            >
              <b-card-text>
                <p>
                  No matter Where you are, Trello stays in sync across all of
                  your devices. Collaborate with your team anywhere, from
                  sitting on the bus to sitting on the beach.
                </p>
              </b-card-text>

              <b-button href="#" variant="secondary" class="mr-2">
                App Store
              </b-button>

              <b-button href="#" variant="secondary">
                Google Play
              </b-button>
            </b-card>
          </div>
        </b-col>
      </b-row>

      <b-row align-h="center" class="mb-5">
        <b-col>
          <h3 class="text-center">Start Planning Today</h3>
          <p class="text-center">
            Sign up and become one of the millions of people around the world
            using Trello to get more done.
          </p>
          <div class="text-center">
            <b-button :to="{ name: 'signup' }" variant="success">
              Get Started - It's Free!
            </b-button>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      search:'',
      slide:'',
      img:[
        {
          value:'No matter Where you are, Trello stays in sync across all of your devices. Collaborate with your team anywhere, from sitting on the bus to sitting on the beach.',
          key:'0'
        },
        {
          value:'No matter Where you are, Trello stays in sync across all of your devices. Collaborate with your team anywhere, from sitting on the bus to sitting on the beach.',
          key:'1'
        },
        {
          value:'No matter Where you are, Trello stays in sync across all of your devices. Collaborate with your team anywhere, from sitting on the bus to sitting on the beach.',
          key:'2'
        },
        {
          value:'No matter Where you are, Trello stays in sync across all of your devices. Collaborate with your team anywhere, from sitting on the bus to sitting on the beach.',
          key:'3'
        },
        {
          value:'No matter Where you are, Trello stays in sync across all of your devices. Collaborate with your team anywhere, from sitting on the bus to sitting on the beach.',
          key:'4'
        }
      ]
    }
  },
  computed:{
    defaultHeadClass(){
      if (this.fixed){
        return  " custom-header shadow fixed-top border-bottom bg-white "
      }else {
        return " custom-header shadow border-bottom bg-white "
      }
    }
  },
  mounted() {
    // whereGo()
  },
  methods: {
    whereGo(){
      console.log('11111');
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
// h3 {
//   margin: 40px 0 0;
// }
// ul {
//   list-style-type: none;
//   padding: 0;
// }
// li {
//   display: inline-block;
//   margin: 0 10px;
// }
// a {
//   color: #42b983;
// }
.home-card-0 {
  height: 400px;
  background: linear-gradient(#3eb9de, #3a80de);
}

.home-card-1 {
  height: 300px;
  background: linear-gradient(#696cbf, #e2859f);
}

.home-card-2 {
  height: 200px;
  background: linear-gradient(to right, #3eb9de, #3a80de);
}
.custom-header{
  z-index: 99999;
}
.shadow {
  // -webkit-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
}
.border-bottom {
  border-bottom: 1px solid #dee2e6 !important;
}
</style>

<template>
  <div>
    <div v-if="!lost">
      <div v-if="questions.length">
        <blockquote class="col-sm-8 col-sm-offset-2">
          <h5>{{getQuestion}}</h5>
          <small>Adele</small>
        </blockquote>
        <div class="align-center">
          <div @click="next" class="btn btn-success">{{getCorrect}}</div>
          <div @click="lose" class="btn btn-default">{{getIncorrect}}</div>
        </div>
      </div>
      <div v-if="!questions.length">
        <img src="http://i.imgur.com/vB9B5.gif" alt="You won">
      </div>
    </div>
    <div v-if="lost">
      <h4>Adele set you on fire (and the rain too)</h4>
      <img src="https://m.popkey.co/1b7a7d/qxarb.gif" alt="You lost">
    </div>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    data () {
      return {
        lost: false,
        questions: [
          {
            message: `Hello, it's me. I was wondering if after all these years you'd like to meet`,
            correct: 'Sure',
            incorrect: 'No way rain pyro'
          },
          {
            message: `To go over everything`,
            correct: `Let's do this together`,
            incorrect: 'You would flatten me super whale sized bitch'
          },
          {
            message: `They say that time's supposed to heal ya, But I ain't done much healing`,
            correct: '*hug*',
            incorrect: '*You'
          },
          {
            message: `Hello, can you hear me?`,
            correct: 'Yes',
            incorrect: `Yes but i'm not answering`
          },
          {
            message: `I'm in California dreaming about who we used to be, when we were younger and free`,
            correct: 'Going',
            incorrect: `Going but without you, prehistoric old bone sack`
          },
          {
            message: `I've forgotten how it felt before the world fell at our feet`,
            correct: 'We were together',
            incorrect: `You were eating and the floor collapsed`
          },
          {
            message: `There's such a difference between us and a million miles`,
            correct: 'We can adapt',
            incorrect: `Moving far away because i can see your ass from here`
          },
          {
            message: `Hello from the other side, I must have called a thousand times`,
            correct: 'Sorry, phone on the other trousers',
            incorrect: `Adeleted you from my phone`
          },
          {
            message: `To tell you I'm sorry for everything that I've done, but when I call you never seem to be home`,
            correct: 'I forgive you',
            incorrect: `Fucking shit factory, stop spamming`
          }
        ]
      }
    },
    methods: {
      next () {
        this.questions.splice(0, 1)
      },
      lose () {
        this.lost = true
      }
    },
    computed: {
      getQuestion () {
        return this.questions[0].message
      },
      getCorrect () {
        return this.questions[0].correct
      },
      getIncorrect () {
        return this.questions[0].incorrect
      }
    }
  }
</script>

<style scoped>
  p {
    color: forestgreen;
  }

  blockquote {
    text-align: center;
    float: none;
    border: none;
  }
</style>

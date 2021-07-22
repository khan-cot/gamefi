<template>
  <div class="wrapper col-flex" id="ourteam">
    <Dialog v-model="dialog" :data="person" @next="next" @prev="prev"/>
    <h1 class="title">Our Team</h1>
    <div class="grid">
      <div v-for="(member, i) in members" :key="i"
           class="member" @click.stop="openDialog(member, i)">
        <img alt :src="`members/${member.image}`"/>
        <div class="member-info">
          <div class="info-name">{{ member.name }}</div>
          <div class="info-title">{{ member.title }}</div>
        </div>
      </div>
    </div>
    <h1 class="title advisor" id="advisors">Advisors</h1>
    <div class="grid">
      <div v-for="(member, i) in advisors" :key="i"
           class="member" @click.stop="openDialog(member, i)">
        <img alt :src="`members/${member.image}`"/>
        <div class="member-info">
          <div class="info-name">{{ member.name }}</div>
          <div class="info-title">{{ member.title }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Dialog from "@/components/Dialog";

export default {
  name: "Team",
  components: {Dialog},
  data() {
    return {
      dialog: false,
      person: null,
      index: 0,
      members: [
        {
          name: 'My Nguyen',
          title: 'Head of Marketing & Operation',
          image: 'member.png',
          // links: [{href: '', img: 'linkedin.svg'}],
          descriptions: [
              'My owns 5+ years of experience in Corporate Communications at SmartOSC, a premium e-commerce agency with more than 500 clients around the world.',
              'She was also a co-founder and Executive Director in JunctionxHaNoi, Vietnam’s first hackathon.'
          ],
        },
        {
          name: 'Hai Duong',
          title: 'Head of Technology',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/haicon2321993', img: 'linkedin.svg'}],
          descriptions: [
              'Hai is the former Director Of Product Development in CyRadar, Top 20 Cyber Security Innovators in 2019 ranked Technology Innovation magazine.',
              'He has 7 years of experience in the development and maintenance of large-scale products.'
          ],
        },
        {
          name: 'Hieu Ha',
          title: 'Head of Security',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/hieuhatrung/', img: 'linkedin.svg'}],
          descriptions: [
              'Hieu has 5+ years of experience performing penetration testing, security auditing, and vulnerability assessments following OWASP, PTES Framework standards.',
              'He is a renowned penetration test expert/ coach with more than 12,000 followers.'
          ]
        },
        {
          name: 'Linh Do',
          title: 'Head of Quality',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/linh-do-29b95a27/', img: 'linkedin.svg'}],
          descriptions: [
            'Linh is the holder of HDSE (Higher Diploma in Software Engineering) with 10 years of experience in quality assurance.',
            'She used to work for Optimizely to provide digital experience solutions to Microsoft and eBay.'
          ],
        },
        {
          name: 'Hong',
          title: 'BA',
          image: 'member.png',
          // links: [{href: 'https://www.linkedin.com/in/hoa-lee/', img: 'linkedin.svg'}],
          descriptions: [
              'Hong has years of experience as a business analyst for outsourcing and blockchain projects before joining the GameFi team.',
              'She can speak and write in different languages, French, English and Japanese.'
          ]
        },
        {
          name: 'Ha',
          title: 'Designer',
          image: 'member.png',
          // links: [{href: 'https://www.linkedin.com/in/hoa-lee/', img: 'linkedin.svg'}],
          descriptions: [
            'Ha is an all-rounded graphic designer with 5 years in various industries such as brand design, illustration, UI design, UX consultant.',
            'Her expertise is creating user experience solutions in high-technology websites or mobile apps.'
          ]
        },
        {
          name: 'Hoang',
          title: 'Developer',
          image: 'member.png',
          // links: [{href: 'https://www.linkedin.com/in/thanh-tung-a87262142/', img: 'linkedin.svg'}],
          descriptions: [
            'Hoang is a driven developer with 4 years of broad experience in software development and 2 years in the blockchain area.',
            'Hoang is a crypto enthusiast and shows a high level of knowledge and skills in Blockchain.'
          ],
        },
      ],
      advisors: [
        {
          name: 'Thi Truong',
          title: 'Executive Advisor',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/mangcut/', img: 'linkedin.svg'}],
          descriptions: [
            'Thi is the founder of PolkaFoundry. He is also the incubator of a couple of blockchain projects such as Faraland game, Bunicorn exchange, etc.',
            'Before founding PolkaFoundry, Thi worked for Kyber Network and FPT Software.',
          ],
        },
        {
          name: 'Hatu',
          title: 'Advisor',
          image: 'member.png',
          // links: [],/
          descriptions: [
              'Hatu is the co-founder, chief marketing, and strategy in Dao Maker. He defines himself as an analyst with the business intuition necessary to analyze opportunities for growth.',
              'Before co-founding Dao Maker, he had years of experience in analytical roles, marketing, management, and entrepreneurial ventures.'
          ]
        }
      ]
    }
  },
  methods: {
    openDialog(data, index) {
      this.index = index
      this.person = data
      this.dialog = true
    },
    next() {
      let list = []
      if(this.members.findIndex(p => p.name === this.person.name) !== -1) {
        list = this.members
      } else {
        list = this.advisors
      }
      let index = this.index + 1
      if (this.index === list.length - 1) {
        index = 0
      }
      this.person = list[index]
      this.index = index
    },
    prev() {
      let list = []
      if(this.members.findIndex(p => p.name === this.person.name) !== -1) {
        list = this.members
      } else {
        list = this.advisors
      }
      if (this.index === 0) {
        this.index = list.length - 1
      } else {
        this.index--
      }
      this.person = list[this.index]
    },
  }
}
</script>

<style scoped>
.wrapper {
  padding: 40px 0 var(--padding-section);
  position: relative;
  background: #0A0A0A;
}

h1.title {
  background: url("../assets/team.png");
  background-size: cover;
  aspect-ratio: 1440/231;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 32px;
  line-height: 40px;
  text-transform: uppercase;
}

h1.title.advisor {
  background: url("../assets/advisor.png");
  background-size: cover;
  margin-top: 120px;
}

.grid {
  padding: 0 var(--padding-section);
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: auto;
}

.member {
  position: relative;
  padding: 32px 4px 24px;
  cursor: pointer;
}

.member img {
  width: 100%;
  position: relative;
  z-index: 1;
}

.member:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 100%;
  background: var(--primary);
  transition: bottom 0.5s;
}

.member:hover:before {
  bottom: 0;
}

.member-info {
  position: relative;
  z-index: 1;
  margin: 22px 6px 4px;
}

.info-name {
  font-weight: bold;
  font-size: 24px;
  line-height: 36px;
  margin-bottom: 4px;
}

.info-title {
  font-weight: 600;
  font-size: 14px;
  line-height: 24px;
  color: var(--primary);
}

.member:hover .info-name,
.member:hover .info-title {
  transition: 0.5s;
  color: #0A0A0A;
}

@media screen and (max-width: 600px) {
  .grid {
    grid-template-columns: 1fr 1fr;
    grid-gap: 12px;
  }
}
</style>
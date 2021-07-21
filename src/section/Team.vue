<template>
  <div class="wrapper col-flex" id="ourteam">
    <Dialog v-model="dialog" :data="person" @next="next" @prev="prev"/>
    <h1 class="title">Our Team</h1>
    <div class="grid">
      <div v-for="(member, i) in members" :key="i"
           class="member" @click.stop="openDialog(member, i)">
        <img alt :src="`members/${member.image}`"/>
        <div class="info">
          <div class="info-btn">Discover</div>
        </div>
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
          name: 'Thi Truong',
          title: 'Executive Advisor',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/mangcut/', img: 'linkedin.svg'}],
          descriptions: [
            'Founder and CEO of PolkaFoundry and Red Kite; incubator of Faraland and KabyArena.',
            'Mr. Thi has been a blockchain soldier with hands-on, in-depth expertise in the blockchain area for many years. He started as a Solution Architect, then a Director at FPT, Vietnam\'s biggest IT company. He is the former Product Manager in Kyber Network, one of Asia’s most successful blockchain projects, before founding PolkaFoundry in 2018.',
          ],
        },
        {
          name: 'My Nguyen',
          title: 'Head of Marketing & Operation',
          image: 'member.png',
          // links: [{href: '', img: 'linkedin.svg'}],
          descriptions: [
            'Ms. My owns 5+ years experience in Corporate Communications at SmartOSC, a premium ecommerce agency with more than 500 clients around the world. In line with her passion for technologies, My later co-founded and undertook the Executive Director position in JunctionxHaNoi, Vietnam’s first hackathon in 2019.',
          ],
        },
        {
          name: 'Linh Do',
          title: 'QA Lead',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/linh-do-29b95a27/', img: 'linkedin.svg'}],
          descriptions: [
            'Holder of HDSE (Higher Diploma in Software Engineering) with 10 years of experience in QA.',
            'Ms. Linh has a demonstrated history of working as SQA Engineer for renowned global corporations including Optimizely, a platform that provides digital experience solutions to Microsoft, IBM and Ebay. As a QA Lead, she not only shows exceptional technical knowledge and analytical skills but also proves to be a supported spirit leader.'
          ],
        },
        {
          name: 'Hai Duong',
          title: 'Tech Lead',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/haicon2321993', img: 'linkedin.svg'}],
          descriptions: [
            'Former Director Of Product Development in CyRadar, Top 20 Cyber Security Innovators in 2019 ranked by US magazine Technology Innovation.',
            'Prior to joining GameFi, Hai has 7 years of experience in the development and maintenance of large-scale products in first-tier technology companies, FPT Corp and CyRadar. He is good at leading the tech team building products from 0 to 1 and achieving rapid growth.'
          ],
        },
        {
          name: 'Thanh Tung',
          title: 'Blockchain Developer',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/thanh-tung-a87262142/', img: 'linkedin.svg'}],
          descriptions: [
            'A Fullstack Developer with 5+ years of broad experience in JavaScript/ES6 & NodeJs & ReactJs/React Native.',
            'Mr. Tung is a crypto enthusiast and shows a high level of knowledge and skills in Blockchain, Rust, and Solidity languages. Tung has previously been one of the core developers in some blockchain-based projects such as PolkaFoundry and Red Kite launchpad.'
          ],
        },
        {
          name: 'Hieu Ha',
          title: 'Senior Penetration Tester',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/hieuhatrung/', img: 'linkedin.svg'}],
          descriptions: [
              'A penetration test expert/coach with more than 12,000 followers.',
              'Hieu devotes to performing penetration testing, security auditing, and vulnerability assessments following OWASP, PTES Framework standards. He has 5+ years of experience working with web applications and web API, Android & iOS applications, IoT devices, network devices, Windows, Linux, and Unix Servers.'
          ]
        },
        {
          name: 'Thanh Hoa',
          title: 'Front-end Developer',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/hoa-lee/', img: 'linkedin.svg'}],
          descriptions: [
              'A driven front-end developer with 8 years of experience.',
              'Hoa has consolidated experience in the context of experimental and real-world deployments concentrating primarily on HTML, CSS, JavaScript, JQuery, Angular JS, XML, and Bootstrap. He is proficient in developing responsive front-end solutions, providing personalized experience to users, and reducing the workload on the back-end.'
          ]
        },
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
      let index = this.index + 1
      if(this.index === this.members.length -1) {
        index = 0
      }
      this.person = this.members[index]
      this.index = index
    },
    prev() {
      if(this.index === 0) {
        this.index = this.members.length - 1
      } else {
        this.index--
      }
      this.person = this.members[this.index]
    },
  }
}
</script>

<style scoped>
.wrapper {
  padding: var(--padding-section);
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
  margin-bottom: 120px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: auto;
}

.member {
  position: relative;
}

.member img {
  width: 100%;
}

.member:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 100%;
  background: #6BE04766;
  transition: bottom 0.5s;
}

.member:hover:after {
  bottom: 0;
}

.member:hover .info {
  opacity: 1;
}

.info {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 2;
  padding: 7%;
  opacity: 0;
  transition: opacity 0.5s;
  display: flex;
  align-items: center;
  justify-content: center;
}

.info-name {
  font-weight: bold;
  font-size: 28px;
  line-height: 36px;
  margin-bottom: 4px;
}

.info-title {
  font-weight: 600;
  font-size: 16px;
  line-height: 28px;
  margin-bottom: 8px;
}

.info-btn {
  padding: 16px 80px;
  cursor: pointer;
  background: #0A0A0A;
  color: var(--primary);
}

.info-shortcut span {
  margin-left: 4px;
  color: #0DDDFB;
  cursor: pointer;
}

.info-link {
  display: flex;
  align-items: center;
  margin-top: 4px;
}

.member-info {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 4%;
  color: #0A0A0A;
  background: linear-gradient(180deg, rgba(114, 243, 75, 0) 0%, #72F34B 78.65%);
}

.member:hover .member-info {
  display: none;
}

@media screen and (max-width: 600px) {
  .grid {
    grid-template-columns: 1fr 1fr;
    grid-gap: 12px;
  }
}
</style>
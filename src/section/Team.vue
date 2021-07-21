<template>
  <div class="wrapper col-flex" id="ourteam">
    <Dialog v-model="dialog" :data="person"/>
    <h1 class="title">Our Team</h1>
    <div class="grid">
      <div v-for="(member, i) in members" :key="i"
           class="member" @click.stop="openDialog(member)">
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
      members: [
        {
          name: 'Thi Truong',
          title: 'Co-founder & CEO',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/mangcut/', img: 'linkedin.svg'}],
          descriptions: [
            'Thi has been a blockchain soldier with hands-on in-depth experience in blockchain area for several years.',
            'He started as a Software Engineer, then Solution Architect, then a Director at FPT Corp. After leaving FPT, he joined Kyber Network, one of the most successful blockchain projects in Asia, as a Product Manager.',
            'Thi founded PolkaFoundry at the end of 2018 after getting frustrated with blockchain dapps\' UX, with the determination to make the benefits of blockchain more accessible to normal people.'
          ],
          shortcut: 'Former senior manager at Kyber Network, a blockchain solder with hands-on in-dept experience for many years...'
        },
        {
          name: 'Ron Nguyen',
          title: 'Head of Partnerships',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/duyhn/', img: 'linkedin.svg'}],
          descriptions: [
            'A graduate of RMIT in Melbourne, Australia, armed with 10 years of experience in marketing, Ron has gained experience working with small to large companies in management positions, including Line Vietnam, NHG, and Enterprise Rent-a-Car.',
            'He is proficient in liaising with influencers and brand partners to forge strategic alliances, and building partnerships to deliver branding solutions.'
          ],
          shortcut: 'A graduate of RMIT in Melbourne, Australia, armed with 10 years of experience in marketing...'
        },
        {
          name: 'Trang Mai',
          title: 'Head of R&D',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/trangmx/', img: 'linkedin.svg'}],
          descriptions: [
            'Holding a Ph.D. and Postdoc from Kyoto University in Japan, Trang has won several world-class academic awards and co-authored many books.',
            'Trang is leading PolkaFoundry’s research efforts on current challenging blockchain frontiers, including quantum-resistant cryptography, multi-party computation, and atomic cross-chain operations.'
          ],
          shortcut: 'Holding a Ph.D. from Kyoto University in Japan, Trang has won several world-class academic awards...'
        },
        {
          name: 'Huy Hoang',
          title: 'Head of Platform Services',
          image: 'member.png',
          links: [{href: '', img: 'linkedin.svg'}],
          descriptions: [
            'Huy has over 10 years of experience working directly with large-scale clients and IT vendors in Japan, including 3 years in the blockchain area.',
            'He is known for his skills and insights about decentralization protocol architecture, system scalability and security, and DeFi solutions.'
          ],
          shortcut: 'An expert in decentralization protocols with 10+ years of experience including 3 years in the blockchain area...'
        },
        {
          name: 'Luong Hoa',
          title: 'Lead Engineer',
          image: 'member.png',
          links: [{href: 'https://www.linkedin.com/in/luonghoa/', img: 'linkedin.svg'}],
          descriptions: [
            'Luong is a seasoned Software Engineer with a demonstrated history of working in the IT and services industry, including the position as a Researcher at Nomura Research Institute, Japan.',
            'With years of experience developing the core of blockchain, he is actively involving in the rebuild of PolkaFoundry on Substrate framework.'
          ],
          shortcut: 'A seasoned blockchain engineer, former researcher at Nomura Research Institute in Tokyo...'
        }
      ],
      advisors: [
        {
          name: 'Lester Lim',
          title: 'Strategy Advisor',
          image: 'lesterlim.png',
          links: [{href: 'https://www.linkedin.com/in/lesterlim15/', img: 'linkedin.svg'}],
          descriptions: [
            'Founder of X21 Digital, also Strategic Advisor to MahaDao & Finxflo, etc.',
            'Lester guides PolkaFoundry on strategy, partnership and offers advice on various matters to help avoid mistakes and innovate faster to realize its vision.'
          ],
          shortcut: 'Founder of X21 Digital, also Strategic Advisor to MahaDao & Finxflo...'
        },
        {
          name: 'Garlam Won',
          title: 'Marketing Advisor',
          image: 'garlam.png',
          links: [{href: 'https://www.linkedin.com/in/garlam/', img: 'linkedin.svg'}],
          descriptions: [
            'Garlam was behind the marketing of some of the most successful projects including Harmony, Sandbox, MANTRADAO, APY.Finance and others.',
            'As an ex-investment banker at JP Morgan & ex-Management consultant at Deloitte, Garlam exerts influence in various parts of the blockchain ecosystem through his in-depth connections with the communities in China, Korea, Canada and the US.'
          ],
          shortcut: 'Behind the marketing of many successful projects including Harmony, Sandbox, MANTRADAO...'
        },
        {
          name: 'Tung Ta',
          title: 'Business Advisor',
          image: 'tung.png',
          links: [{href: 'https://www.linkedin.com/in/ta-son-tung-062454a9/', img: 'linkedin.svg'}],
          descriptions: [
            'Tung Ta, a Forbes 30  Under 30 in 2015, is the co-founder and executive chairman of RikkeiSoft, one of the largest software companies in Vietnam with a strong salesforce in Japan.',
            'Tung is helping PolkaFoundry to expand its ecosystem and form partnerships with key players in the Japanese market. Rikkeisoft also provides PolkaFoundry with talented developers whenever needed.'
          ],
          shortcut: 'Co-founder and executive chairman of RikkeiSoft, one of the largest software companies in Vietnam...'
        },
        {
          name: 'Eric Su',
          title: 'CEO of Exnetwork',
          image: 'eric.png',
          links: [{href: 'https://www.linkedin.com/in/ericsu', img: 'linkedin.svg'}],
          descriptions: [
            'Eric is one of PolkaFoundry’s highly value advisors, bringing immense expertise as an accomplished serial entrepreneur in markets of key strategic importance.',
            'Exnetwork also has direct investment ties with the Polkadot multi-chain. The company’s portfolio includes cross-chain token launchpad Polkastarter and liquidity aggregator Reef Finance — a Polkadot pioneer as the first parachain on Binance. Hence, we relished the opportunity to take into account Eric’s views on the role of PolkaFoundry in the development of DeFi dApps for an interoperable future.'
          ],
          shortcut: 'For our latest Advisor Spotlight, we are delighted to highlight Eric Su, CEO of Exnetwork...'
        },
        {
          name: 'Joe Wong',
          title: 'Advisor',
          image: 'joe.png',
          links: [{href: 'https://twitter.com/khunjoe5', img: 'twitter.svg'}],
          descriptions: [
            'Principal of Fomocraft Ventures & seasoned market of 23 years. CMO and Advisor for MANTRA DAO, Launchpool, FinNexus, Polkastarter and Royale.finance.',
            'Joe is a master of ensuring that a project\'s vision is faithfully executed & communicated to the community.'
          ],
          shortcut: 'Principal of Fomocraft Ventures & seasoned marketer of 23 years...'
        },
      ]
    }
  },
  methods: {
    openDialog(data) {
      // this.person = data
      // this.dialog = true
      return data
    }
  }
}
</script>

<style scoped>
.wrapper {
  padding: var(--padding-article) 100px;;
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
  grid-template-columns: repeat(5, 1fr);
}

.member {
  position: relative;
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
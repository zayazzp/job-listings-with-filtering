<template>
  <div class="wrapper">
    <the-header></the-header>
    <transition name="filter">
      <job-filter v-if="filterOption.length > 0"></job-filter>
    </transition>
    <main>
      <job-listings></job-listings>
    </main>
  </div>
</template>
<script>
import TheHeader from "./components/TheHeader.vue";
import JobListings from "./components/JobListings.vue";
import JobFilter from "./components/JobFilter.vue";
export default {
  components: {
    TheHeader,
    JobListings,
    JobFilter,
  },
  data() {
    return {
      joblist: [
        {
          id: 1,
          company: "Photosnap",
          logo: "/photosnap.svg",
          new: true,
          featured: true,
          position: "Senior Frontend Developer",
          role: "Frontend",
          level: "Senior",
          postedAt: "1d ago",
          contract: "Full Time",
          location: "USA Only",
          languages: ["HTML", "CSS", "JavaScript"],
          tools: [],
        },
        {
          id: 2,
          company: "Manage",
          logo: "/manage.svg",
          new: true,
          featured: true,
          position: "Fullstack Developer",
          role: "Fullstack",
          level: "Midweight",
          postedAt: "1d ago",
          contract: "Part Time",
          location: "Remote",
          languages: ["Python"],
          tools: ["React"],
        },
        {
          id: 3,
          company: "Account",
          logo: "/account.svg",
          new: true,
          featured: false,
          position: "Junior Frontend Developer",
          role: "Frontend",
          level: "Junior",
          postedAt: "2d ago",
          contract: "Part Time",
          location: "USA Only",
          languages: ["JavaScript"],
          tools: ["React", "Sass"],
        },
        {
          id: 4,
          company: "MyHome",
          logo: "/myhome.svg",
          new: false,
          featured: false,
          position: "Junior Frontend Developer",
          role: "Frontend",
          level: "Junior",
          postedAt: "5d ago",
          contract: "Contract",
          location: "USA Only",
          languages: ["CSS", "JavaScript"],
          tools: [],
        },
        {
          id: 5,
          company: "Loop Studios",
          logo: "/loop-studios.svg",
          new: false,
          featured: false,
          position: "Software Engineer",
          role: "FullStack",
          level: "Midweight",
          postedAt: "1w ago",
          contract: "Full Time",
          location: "Worldwide",
          languages: ["JavaScript"],
          tools: ["Ruby", "Sass"],
        },
        {
          id: 6,
          company: "FaceIt",
          logo: "/faceit.svg",
          new: false,
          featured: false,
          position: "Junior Backend Developer",
          role: "Backend",
          level: "Junior",
          postedAt: "2w ago",
          contract: "Full Time",
          location: "UK Only",
          languages: ["Ruby"],
          tools: ["RoR"],
        },
        {
          id: 7,
          company: "Shortly",
          logo: "/shortly.svg",
          new: false,
          featured: false,
          position: "Junior Developer",
          role: "Frontend",
          level: "Junior",
          postedAt: "2w ago",
          contract: "Full Time",
          location: "Worldwide",
          languages: ["HTML", "JavaScript"],
          tools: ["Sass"],
        },
        {
          id: 8,
          company: "Insure",
          logo: "/insure.svg",
          new: false,
          featured: false,
          position: "Junior Frontend Developer",
          role: "Frontend",
          level: "Junior",
          postedAt: "2w ago",
          contract: "Full Time",
          location: "USA Only",
          languages: ["JavaScript"],
          tools: ["Vue", "Sass"],
        },
        {
          id: 9,
          company: "Eyecam Co.",
          logo: "/eyecam-co.svg",
          new: false,
          featured: false,
          position: "Full Stack Engineer",
          role: "Fullstack",
          level: "Midweight",
          postedAt: "3w ago",
          contract: "Full Time",
          location: "Worldwide",
          languages: ["JavaScript", "Python"],
          tools: ["Django"],
        },
        {
          id: 10,
          company: "The Air Filter Company",
          logo: "/the-air-filter-company.svg",
          new: false,
          featured: false,
          position: "Front-end Dev",
          role: "Frontend",
          level: "Junior",
          postedAt: "1mo ago",
          contract: "Part Time",
          location: "Worldwide",
          languages: ["JavaScript"],
          tools: ["React", "Sass"],
        },
      ],
      filterOption: [],
    };
  },
  provide() {
    return {
      joblist: this.joblist,
      filterOption: this.filterOption,
    };
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Spartan:wght@500;700&display=swap");
:root {
  --DesaturatedDarkCyan: hsl(180, 29%, 50%);
  --LightGrayishCyanBG: hsl(180, 52%, 96%);
  --LightGrayishCyanFilterTablets: hsl(180, 31%, 95%);
  --DarkGrayishCyan: hsl(180, 8%, 52%);
  --VeryDarkGrayishCyan: hsl(180, 14%, 20%);
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background-color: var(--LightGrayishCyanBG);
  font-family: "Spartan", sans-serif;
  font-weight: 500;
}
main {
  margin-top: 60px;
}
@keyframes fade {
  from {
    opacity: 0%;
  }
  to {
    opacity: 100%;
  }
}
.filter-enter-active {
  animation: fade 0.1s ease-in;
}
.filter-leave-active {
  animation: fade 0.1s ease-out reverse;
}
</style>

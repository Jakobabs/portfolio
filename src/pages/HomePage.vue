<script setup lang="ts">
import { useWindowSize, useWindowScroll } from "@vueuse/core";
import ExperienceCard from "../components/ExperienceCard.vue";
import Skillcard from "../components/SkillCard.vue";
import Socials from "../components/Socials.vue";
import { useRouter } from "vue-router";

const router = useRouter();
const windowSize = useWindowSize();
const scroll = useWindowScroll({ behavior: "smooth" });

const scrollDown = () => {
  const navbar = document.getElementById("NavBar");
  let offset: number = windowSize.height.value;
  if (navbar !== null) offset -= navbar.clientHeight;
  scroll.y.value = offset;
};
</script>

<template>
  <div
    class="hero min-h-screen min-w-screen bg-fixed"
    style="
      background-image: url(https://www.odu.edu/sites/default/files/program-page/headerimages/electrical-and-computer-engineering-header.jpeg);
    "
  >
    <div class="hero-overlay bg-opacity-60 size-full"></div>
    <div class="hero-content text-left text-neutral-content min-w-screen">
      <div class="absolute left-0 pl-10 md:pl-44">
        <h1 class="mb-5 text-5xl font-bold text-slate-50">Jacob Kelly</h1>
        <h2 class="mb-5 text-slate-100">Electrical & Computer Engineer</h2>
        <Socials :bg="'bg-slate-300'" :gap="'gap-6'" />
      </div>
      <button
        @click="scrollDown"
        class="btn btn-ghost btn-circle absolute bottom-5"
      >
        <span class="material-symbols-outlined scale-175 text-slate-300"
          >keyboard_arrow_down</span
        >
      </button>
    </div>
  </div>
  <div
    class="flex flex-col lg:flex-row justify-center content-center gap-6 bg-base-200 p-8"
  >
    <div class="max-w-80 self-center">
      <h1 class="mb-8 text-4xl font-bold">Eastern Michigan University</h1>
      <p class="mb-3">
        Currently pursuing a Bachelor of Science in Electrical and Computer
        Engineering. My expected graduation date is December 2024.
      </p>
      <p>
        Relevant coursework includes: Circuit Analysis, Controls Systems, Power
        Electronics.
      </p>
    </div>
    <ExperienceCard
      :date="'2024'"
      :title="'Senior Capstone Leader'"
      :text="'Led a team to create a viable product. Generated progress reports and met deadlines.'"
    />
    <div class="flex flex-col">
      <ExperienceCard
        class="mb-6"
        :date="'2023 - Present'"
        :title="'EMU IEE Club'"
        :text="'University club focused on engineering topics and principles.'"
      />
      <ExperienceCard
        :date="'2020 - Present'"
        :title="'Target Corp.'"
        :text="'Employed as Service Advocate, Cart Attendant, Drive-Up, and Specialty Sales.'"
      />
    </div>
  </div>
  <div class="hero py-24">
    <div class="hero-content flex-col">
      <h1 class="mb-8 text-4xl font-bold text-center">
        Key skills and experience
      </h1>
      <p class="mb-3 text-xl font-medium text-center">
        I started learning programming in 2016. Since then I have learned many
        languages, including: Rust, Embedded C, Python, HTML, JavaScript, CSS,
        and Java. In University I learned about inductors, capacitors,
        transistors, and amplifiers. I am very knowledgeable in both electrical
        and computer engineering.
      </p>
    </div>
  </div>
  <div
    class="flex flex-col lg:flex-row justify-center content-center gap-6 p-8"
  >
    <Skillcard
      :icon="'data_object'"
      :title="'Developer'"
      :text="'I have experience in Embedded, Backend, and Full Stack design.'"
    />
    <Skillcard
      :icon="'memory'"
      :title="'Hardware design'"
      :text="'Circuit analysis, power electronics, and PCB design.'"
    />
    <Skillcard
      :icon="'dns'"
      :title="'Networking'"
      :text="'I host my own Unraid server with: Nextcloud, Authentik, HASS, and RDP.'"
    />
    <Skillcard
      :icon="'neurology'"
      :title="'AI'"
      :text="'Applied an Object Detection model using ML and DNN.'"
    />
  </div>
  <div class="hero px-6 py-8 justify-center bg-base-200">
    <div class="hero-content flex-col lg:flex-row">
      <img
        src="/jacobkelly.png"
        class="w-56 md:w-96 rounded-lg shadow-2xl self-start"
      />
      <div class="px-6">
        <h1 class="text-3xl font-bold max-w-80">
          Jacob Kelly: Electrical & Computer Engineer
        </h1>
        <p class="py-6 max-w-96">
          Personally, engineering is not just a career, it's my hobby. I greatly
          enjoy solving problems and learning new skills to do so. I have
          completed many personal projects regarding smart home, robotics,
          electronics, and computer systems. You can look at a few of them
          <a @click="router.push('/projects')" class="link link-primary">here</a
          >. I am FE certified, you can click the badge below for more details.
        </p>
        <h2 class="text-xl font-medium max-w-80">Design tools</h2>
        <p class="py-6 max-w-96">
          Using Kicad I have created multiple PCBs for my embedded projects
          along with Autodesk Fusion 360 for CAD and 3D Printing
        </p>
        <h2 class="text-xl font-medium max-w-80">Development skills</h2>
        <p class="py-6 max-w-96">
          I contributed to a Web App using Tauri and Vue.js. The backend handled
          data manipulation and concurrent http requests. I also wrote this
          entire website!
        </p>
        <div class="flex flex-wrap justify-start md:justify-end gap-3">
          <div class="avatar size-16">
            <div class="rounded">
              <img
                src="https://cdn.icon-icons.com/icons2/2415/PNG/512/html_plain_wordmark_logo_icon_146476.png"
              />
            </div>
          </div>
          <div class="avatar size-16">
            <div class="rounded">
              <img
                src="https://cdn.icon-icons.com/icons2/2415/PNG/512/css_plain_wordmark_logo_icon_146574.png"
              />
            </div>
          </div>
        
          <div class="avatar size-16">
            <div class="rounded">
              <img
                src="https://cdn.icon-icons.com/icons2/2108/PNG/512/javascript_icon_130900.png"
              />
            </div>
          </div>
          <div class="avatar size-16">
            <div class="rounded">
              <img
                src="https://cdn.icon-icons.com/icons2/2107/PNG/512/file_type_python_icon_130221.png"
              />
            </div>
          </div>
          <div class="avatar size-16">
            <div class="rounded">
              <img
                src="https://cdn.icon-icons.com/icons2/2699/PNG/512/rust_lang_logo_icon_169776.png"
              />
            </div>
          </div>
          <a
            class="avatar size-16 cursor-pointer"
            href="https://www.credly.com/badges/986ee904-ad02-423e-a217-c6569475a59f/public_url"
            target="_blank"
            rel="noopener noreferrer"
          >
            <div class="rounded">
              <img src="/fe-exam.png" />
            </div>
          </a>
        </div>
      </div>
    </div>
  </div>
  <div class="flex felx-col justify-center content-center gap-6 py-12">
    <h1 class="text-4xl font-bold">Getting in touch</h1>
  </div>
  <div class="flex flex-col lg:flex-row justify-center gap-6 p-8">
    <Skillcard
      :icon="'mail'"
      :title="'jkelly58@emich.edu'"
      :text="'My preferred method, the best way to get a fast response.'"
    />
    <Skillcard
      :icon="'phone'"
      :title="'(734)-730-5693'"
      :text="'Call during normal hours, text anytime.'"
    />
    <Skillcard
      :icon="'bug_report'"
      :title="'Github repo'"
      :text="'Check out my source code, and active projects.'"
    />
  </div>
</template>

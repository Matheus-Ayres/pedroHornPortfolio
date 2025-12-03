<script setup lang="ts">
import { ref } from 'vue';
import CardEnd from './components/CardEnd.vue';
import Carousel from './components/Carousel.vue';
import SplitText from './components/SplitText.vue';
import ClapperIcon from "@/assets/icons/clapper.png";
import CamIcon from "@/assets/icons/cam.png";
import DesignerIcon from "@/assets/icons/designer.png";
import MotionIcon from "@/assets/icons/motion.png";



const handleAnimationComplete = () => {
  console.log('All letters have animated!');
};


</script>

<template>
  <main class="bg-gradient-to-tr from-black via-purple-600 to-orange-700 min-h-screen ">
    <div class="bg-black/50 min-h-screen">
      <section class="flex flex-row h-full justify-around">

        <article class="px-20 py-60 flex flex-col items-start ">

          <span class="text-Sec text-white text-3xl">
            Olá, <span class="text-SecBold">prazer em ter você aqui!</span>
          </span>
          <SplitText text="PEDRO HORN" class-name="text-Main text-white text-9xl" :delay="100" :duration="0.6"
            split-type="chars" :from="{ opacity: 0, y: 40 }" :to="{ opacity: 1, y: 0 }" :threshold="0.1"
            @animation-complete="handleAnimationComplete" />

          <span class="text-Sec text-white text-xl mt-6">
            Portfólio Profissional
          </span>

        </article>


        <div>
          <img src="@/assets/images/home_pedro.png" alt="Profile Image"
            class="w-full h-full opacity-0 transition-all duration-1000 ease-out animate-fade-in" />
        </div>

      </section>

      <h1 class="text-Main text-5xl text-center text-purple-600 bg-white pt-2 pb-5">Sobre Mim</h1>

      <section class="grid grid-cols-2">
        <article>
          <p class="text-Sec px-20 py-20 text-white text-2xl">
            Sou Pedro Henrique Horn, sou de Guarapuava-PR, especializado em
            <span class="text-SecBold">captação e edição de vídeos, motion design, criação de identidades visuais e
              social media.</span>
            Tenho um olhar muito forte para estética, ritmo e estratégia. Sempre pensando em como cada peça pode gerar
            <span class="text-SecBold">impacto real</span> para marcas negócios e <span
              class="text-SecBold">pessoas.</span>

            <br>
            <br>
            Trabalho desenvolvendo conteúdos e identidades que conectam, atendendo empresas, profissionais e criadores
            que buscam
            qualidade, consistência e presença digital de verdade.
            <br>
            <br>
            Tenho 23 anos, sou casado e pai da Isabella, e é isso que me inspira diariamente a
            evoluir e entregar o meu melhor em cada projeto.
          </p>
        </article>

        <Carousel class="my-auto" />
      </section>

      <section class="flex flex-col items-center">
        <h1 class="text-Main text-5xl text-center text-white">
          O que <span class="text-red-600  [-webkit-text-stroke:1px_white]">você ganha</span>
          com
          <br>
          meus serviços?
        </h1>

        <div class="mt-20 pb-20">
          <div class="grid grid-cols-4 gap-10 ">
            <CardEnd 
              :icon="ClapperIcon"
              title="Audiovisual"
              item1="Reels Produzidos" 
              item2="Comerciais"
              item3="Institucionais"
              item4="Bastidores"
              item5="Conteúdos para Tráfegos"
            />

            <CardEnd 
              :icon="DesignerIcon"
              title="Design Identidades"
              item1="Logos" 
              item2="Mascotes"
              item3="Aplicações Completas (mockups, posts, banners)"
            />

            <CardEnd 
              :icon="MotionIcon" 
              title="Motion Designer"
              item1="Vinhetas"
              item2="Animações 2D"
              item3="Logo Animations"
            />

            <CardEnd 
              :icon="CamIcon" 
              title="Fotografia"
              item1="Produtos"
              item2="Gastronomia"
              item3="Lifestyle"
              item4="Retratos Profissionais"
              item5="Fotos para anúncios"
              item6="Branding e ambientação de empresas"
            />
          </div>
        </div>
      </section>

    </div>
  </main>
</template>


<style scoped>
  @keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1.2s ease-out forwards;
}

</style>
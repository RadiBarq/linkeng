<template>
  <div class="bg-gray-100 h-full">
    <div class="h-2/3 w-full">
      <!-- Hero Image for tablets and above -->
      <img
        src="@/assets/images/home_image.png"
        alt="Hero"
        class="absolute top-0 left-0 w-full h-2/3 object-cover"
      />

      <!-- Hero Image for mobile phones -->
      <img
        src="@/assets/images/home_image_mobile.png"
        alt="Hero"
        class="absolute top-0 left-0 w-full h-2/3 object-cover md:hidden"
      />

      <!-- English Button on top-right -->
      <div class="absolute top-2 md:top-4 right-2 md:right-4">
        <button
          v-if="!isEnglish"
          @click="toggleLanguage"
          class="text-white font-bold px-4 md:px-8 py-4 md:py-8"
        >
          English
        </button>

        <button
          v-if="isEnglish"
          @click="toggleLanguage"
          class="text-white font-bold px-4 md:px-8 py-4 md:py-8"
        >
          عربي
        </button>
      </div>

      <!-- Content centered on the hero -->
      <div
        class="absolute top-1/3 lg:top-1/3 w-3/4 md:w-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-center"
      >
        <!-- Company Logo -->
        <img
          src="@/assets/images/linkeng_logo.png"
          alt="Company Logo"
          class="w-60 md:w-80 mx-auto"
        />

        <!-- Company Title -->
        <h1
          v-if="isEnglish"
          class="text-xl md:text-2xl text-white font-medium mt-16 md:mt-10"
        >
          Your Engineering Solutions, Streamlined
        </h1>

        <!-- Company Title -->
        <h1
          v-if="!isEnglish"
          class="text-xl md:text-2xl text-white font-medium mt-16 md:mt-10"
        >
          حلولك الهندسية بكفاءة
        </h1>

        <!-- Social Links -->
        <div
          class="flex flex-row space-x-4 md:space-x-4 justify-center mt-20 md:mt-12"
        >
          <a
            target="_blank"
            href="https://www.instagram.com/linkeng_ps"
            class="text-blue-500 hover:text-blue-600"
          >
            <img src="@/assets/images/instagram_logo.png" />
          </a>
          <a
            target="_blank"
            href="https://www.linkedin.com/in/link-eng-297829291"
            class="text-blue-400 hover:text-blue-500"
          >
            <img src="@/assets/images/linkedin_logo.png" />
          </a>
          <a target="_blank" href="#" class="text-red-500 hover:text-red-600">
            <img src="@/assets/images/email_logo.png" />
          </a>
          <a href="tel:+970594077792" class="text-red-500 hover:text-red-600">
            <img src="@/assets/images/call_logo.png" />
          </a>
        </div>
      </div>
    </div>

    <!-- English Features Section -->
    <div v-if="isEnglish" class="bg-gray-100 absolute top-2/3 w-full">
      <div class="bg-gray-100 max-w-4xl mx-auto text-left pb-10 pt-10">
        <!-- Bullet Points -->
        <ul class="space-y-6 pl-4 md:pl-4">
          <li
            class="flex flex-col md:flex-row space-y-4 md:space-y-0 items-start md:items-center"
          >
            <img
              class="h-10 mr-0 md:mr-10"
              src="@/assets/images/first_point_icon.png"
            />
            <span class="text-black font-semibold"
              >Linkeng is your trusted partner for streamlined engineering
              solutions. With our extensive network of engineers in various
              fields (architectural, structural, electrical, and mechanical), we
              provide tailored services to companies and offices during
              demanding times.</span
            >
          </li>
          <li
            class="flex flex-col md:flex-row space-y-4 md:space-y-0 items-start md:items-center"
          >
            <img
              class="w-10 mr-0 md:mr-10"
              src="@/assets/images/second_point_icon.png"
            />
            <span class="text-black font-semibold"
              >Our role is to connect with your company or office, understand
              the task at hand, and select the most qualified engineer from our
              network. We handle the supervision and ensure impeccable quality,
              relieving you of the need for direct oversight.
            </span>
          </li>
          <li
            class="flex flex-col md:flex-row space-y-4 md:space-y-0 items-start md:items-center"
          >
            <img
              class="w-10 mr-0 md:mr-10"
              src="@/assets/images/third_point_icon.png"
            />
            <span class="text-black font-semibold"
              >With Linkeng, you can focus on your core business while we
              efficiently manage the engineering tasks. Experience professional
              expertise, efficient communication, and timely project delivery
              with Linkeng.</span
            >
          </li>
          <!-- ... add more features as needed ... -->
        </ul>
      </div>
    </div>

    <!-- Arabic Features Section -->
    <div v-if="!isEnglish" class="bg-gray-100 absolute top-2/3 w-full">
      <div class="bg-gray-100 max-w-4xl mx-auto text-left pb-10 pt-10">
        <!-- Bullet Points -->
        <ul class="space-y-6 ml-4 pr-4 md:ml-4 md:pr-4">
          <li
            class="flex flex-col-reverse md:flex-row space-y-4 md:space-y-0 items-end md:items-center"
          >
            <span class="text-black font-semibold text-right mt-4 md:mt-0"
              >لينك إنج هي الشريك الموثوق لحلول الهندسة الموجهة. من خلال شبكتنا
              الواسعة من المهندسين في مجالات متنوعة (معمارية، إنشائية، كهربائية،
              وميكانيكية)، نقدم خدمات مخصصة للشركات والمكاتب خلال الأوقات
              المليئة بالتحديات.</span
            >
            <img
              class="h-10 ml-0 md:ml-10"
              src="@/assets/images/first_point_icon.png"
            />
          </li>
          <li
            class="flex flex-col-reverse md:flex-row space-y-4 md:space-y-0 items-end md:items-center"
          >
            <span class="text-black font-semibold text-right mt-4 md:mt-0"
              >دورنا هو الاتصال مع شركتك أو مكتبك، فهم المهمة المطلوبة، واختيار
              أكفأ المهندسين من شبكتنا. نحن ندير عملية المراقبة ونضمن الجودة
              المتفوقة، مما يخلصك من الحاجة للإشراف المباشر.
            </span>
            <img
              class="w-10 ml-0 md:ml-10"
              src="@/assets/images/second_point_icon.png"
            />
          </li>
          <li
            class="flex flex-col-reverse md:flex-row space-y-4 md:space-y-0 items-end md:items-end"
          >
            <span class="text-black font-semibold text-right mt-4 md:mt-0"
              >مع لينك إنج، يمكنك التركيز على نشاطك الأساسي بينما ندير المهام
              الهندسية بكفاءة. اكتشف الخبرة المهنية، والتواصل الفعال، والتسليم
              في الوقت المناسب مع لينك إنج.
            </span>
            <img
              class="w-10 ml-0 md:ml-10"
              src="@/assets/images/third_point_icon.png"
            />
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
let isEnglish = ref(true);

function toggleLanguage() {
  isEnglish.value = !isEnglish.value;
}
</script>

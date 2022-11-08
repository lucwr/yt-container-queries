<script setup></script>

<template>
  <div class="bg-sky-700 text-white rounded-sm leading-snug">
    <div class="flex gap-3 sm:gap-0 flex-col sm:flex-row justify-around items-center text-center px-3 py-4">
      <div class="uppercase font-bold">
        <div class="location-city">Toronto</div>
        <div class="location-country">Canada</div>
      </div>
      <div>
        <img
          src="../assets/sunny.svg"
          alt="sunny"
          class="w-16"
        />
      </div>
      <div>
        <div class="text-xl">23 &#8451;</div>
        <div class="">Partly Cloudy</div>
      </div>
    </div>

    <div class="flex flex-col sm:flex-row gap-1 justify-around text-center my-10">
      <div class="day-container text-sm px-2 py-4">
        <div class="uppercase">Mon</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/sunny.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4">
        <div class="uppercase">Tue</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/rain.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4">
        <div class="uppercase">Wed</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/cloudy.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4 hidden sm:block">
        <div class="uppercase">Thu</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/partly-cloudy.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4 hidden sm:block">
        <div class="uppercase">Fri</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/rain.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4 hidden sm:block">
        <div class="uppercase">Sat</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/sunny.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
      <div class="day-container text-sm px-2 py-4 hidden sm:block">
        <div class="uppercase">Sun</div>
        <div class="w-7 py-1 mx-auto">
          <img src="../assets/sunny.svg" alt="weather icon" />
        </div>
        <div class="">
          <div>23 &#8451;</div>
          <div>12 &#8451;</div>
        </div>
      </div>
    </div>
  </div>
</template>

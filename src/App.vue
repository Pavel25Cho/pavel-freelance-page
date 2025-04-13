<template>
    <div class="flex flex-col gap-20 bg-blue-400 md:pt-20 pt-5 md:pb-40 pb-20 text-gray-800">
        <div id="promo" class="flex lg:flex-row flex-col justify-center-safe">
            <div class="max-w-md overflow-hidden rounded-xl bg-white shadow-md md:max-w-2xl lg:m-4 md:mx-auto m-4 mb-10">
                <div class="md:flex">
                    <div class="md:shrink-0">
                        <img
                            class="w-full object-cover aspect-square md:max-h max-h-60 md:h-full md:w-48"
                            src="/src/assets/img/me.webp"
                            alt="Personal image"
                        />
                    </div>
                    <div class="p-8">
                        <div class="font-semibold tracking-wide text-blue-400 uppercase">Радионов Кирилл</div>
                        <p class="mt-1 block text-lg leading-tight font-medium">
                            Разработка сайтов/ботов под ключ, любой сложности
                        </p>
                        <p class="mt-2 text-gray-500">
                            Работаю программистом более 3х лет. Занимаюсь разработкой сайтов и ботов любой сложности. Работа под ключ, по договору, с предоставлением всех чеков.
                        </p>
                    </div>
                </div>
            </div>
    
            <div class="flex flex-col m-4 lg:gap-0 gap-5 lg:justify-around">
                <a 
                    v-for="(button, ind) in buttons"
                    :key="ind"
                    :href="button.link"
                    :target="button.target"
                    :class="['rounded-4xl shadow-md text-center lg:py-1 py-4 px-3 border-2 ease-in-out duration-200 bg-white border-white hover:bg-blue-400 hover:text-white hover:scale-105', button.class]"
                >
                    {{ button.title }}
                    <svg v-if="button.svg" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="ml-1 mt-1"><path d="M3 15v4c0 1.1.9 2 2 2h14a2 2 0 0 0 2-2v-4M17 9l-5 5-5-5M12 12.8V2.5"/></svg>
                    <svg v-if="button.telegram" width="20px" height="20px" viewBox="-2.4 -2.4 28.80 28.80" fill="currentColor" xmlns="http://www.w3.org/2000/svg" class="ml-1 mt-1"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path fill-rule="evenodd" clip-rule="evenodd" d="M23.1117 4.49449C23.4296 2.94472 21.9074 1.65683 20.4317 2.227L2.3425 9.21601C0.694517 9.85273 0.621087 12.1572 2.22518 12.8975L6.1645 14.7157L8.03849 21.2746C8.13583 21.6153 8.40618 21.8791 8.74917 21.968C9.09216 22.0568 9.45658 21.9576 9.70712 21.707L12.5938 18.8203L16.6375 21.8531C17.8113 22.7334 19.5019 22.0922 19.7967 20.6549L23.1117 4.49449ZM3.0633 11.0816L21.1525 4.0926L17.8375 20.2531L13.1 16.6999C12.7019 16.4013 12.1448 16.4409 11.7929 16.7928L10.5565 18.0292L10.928 15.9861L18.2071 8.70703C18.5614 8.35278 18.5988 7.79106 18.2947 7.39293C17.9906 6.99479 17.4389 6.88312 17.0039 7.13168L6.95124 12.876L3.0633 11.0816ZM8.17695 14.4791L8.78333 16.6015L9.01614 15.321C9.05253 15.1209 9.14908 14.9366 9.29291 14.7928L11.5128 12.573L8.17695 14.4791Z"></path></g></svg>
                </a>
            </div>
        </div>

        <div id="examples" class="flex flex-col items-center-safe lg:gap-6 gap-8">
            <h2 class=" text-2xl text-white font-semibold tracking-wide uppercase">Примеры работ:</h2>
            <div class="flex flex-col lg:flex-row justify-center lg:gap-6 gap-8">
                <a 
                    v-for="(site, ind) in sites"
                    :key="ind"
                    :href="site.link"
                    target="_blank"
                    class="max-w-md overflow-hidden rounded-xl bg-white shadow-md lg:mx-0 mx-4 text-blue-400 hover:underline hover:scale-105 ease-in-out duration-200"
                >
                    <div class="md:flex md:flex-col md:items-center">
                        <img
                            class="w-full object-cover max-h-60"
                            :src="getImageUrl(site.img)"
                            :alt="site.link"
                        />
                        <div class="flex flex-row p-2 font-semibold tracking-wide uppercase">
                            {{ site.link }}
                            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="ml-2 mt-0.5"><g fill="none" fill-rule="evenodd"><path d="M18 14v5a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8c0-1.1.9-2 2-2h5M15 3h6v6M10 14L20.2 3.8"/></g></svg>
                        </div>
                    </div>
                </a>
            </div>
        </div>

        <div id="price" class="flex flex-col items-center-safe lg:gap-6 gap-8 mb-10">
            <h2 class="text-2xl text-white font-semibold tracking-wide uppercase">Прайс-лист:</h2>
            <div 
                v-for="(price, ind) in prices"
                :key="ind"
                class="flex items-end w-2xl max-w-[92%] rounded-4xl shadow-md text-center py-2 px-3 lg:mx-0 mx-4 bg-white"
            >
                <span>{{ price.title }}</span>
                <div class="flex-1 bg-[url(src/assets/svg/dots.svg)] h-0.25 bg-repeat mb-1.5 mx-1"></div>
                <span>от {{ price.price }} ₽</span>
            </div>
            <div class="flex items-end justify-center w-2xl max-w-[92%] rounded-4xl shadow-md text-center py-2 px-3 bg-white">
                * Цена за проект обговаривается индивидуально, итоговая зависит от объема работ
            </div>
        </div>

        <div id="contact" class="flex flex-col items-center-safe lg:gap-6 gap-8">
            <a 
                href="https://t.me/pave1cho"
                target="_blank"
                class="rounded-4xl shadow-md text-center lg:py-1 py-4 px-3 border-2 ease-in-out duration-200 bg-white border-white text-blue-400 hover:scale-105"
            >
                <span>Написать</span>
                <img
                    class="w-full object-cover max-h-60"
                    src="/src/assets/img/tme.webp"
                    alt="Telegram QR"
                />
                <div class="flex flex-row p-2 font-semibold tracking-wide uppercase">
                    https://t.me/pave1cho
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="ml-2 mt-0.5"><g fill="none" fill-rule="evenodd"><path d="M18 14v5a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8c0-1.1.9-2 2-2h5M15 3h6v6M10 14L20.2 3.8"/></g></svg>
                </div>
            </a>
        </div>
    </div>
</template>

<script>
import buttons  from "./assets/data/promo-buttons.json";
import sites    from "./assets/data/sites-examples.json";
import prices   from "./assets/data/prices.json";

export default {
    data() {
        return {
            buttons: buttons,
            sites:   sites,
            prices:  prices
        }
    }, 
    methods: {
        getImageUrl(name) {
            // note that this does not include files in subdirectories
            return new URL(`/src/assets/img/${name}.webp`, import.meta.url).href
        }
    }
}
</script>

<script setup>
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItems,
  MenuItem,
  TransitionRoot,
} from "@headlessui/vue";
import { ref } from "vue";
import {
  ChevronDownIcon,
  ChevronUpIcon,
  Bars3Icon,
} from "@heroicons/vue/20/solid";

const navigation = [
  { name: "Dashboard", href: "#", current: true },
  { name: "Team", href: "#", current: false },
  { name: "Projects", href: "#", current: false },
  { name: "Calendar", href: "#", current: false },
];
const showDropdownFeatures = ref(false);
const showDropdownCompany = ref(false);

const toggleDropdownFeatures = () => {
  showDropdownFeatures.value = !showDropdownFeatures.value;
  showDropdownCompany.value = false;
};

const toggleDropdownCompany = () => {
  showDropdownCompany.value = !showDropdownCompany.value;
  showDropdownFeatures.value = false;
};

// logo Sponsor
const features = [
  { img: "/images/icon-todo.svg", name: "Todo List" },
  { img: "/images/icon-calendar.svg", name: "Calendar" },
  { img: "/images/icon-reminders.svg", name: "Reminders" },
  { img: "/images/icon-planning.svg", name: "Planning" },
];
</script>

<template>
  <Disclosure as="nav" class="bg-transparent">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 right-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <DisclosureButton
            class="relative inline-flex items-center justify-center rounded-md p-2 text-black hover:bg-black hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          >
            <span class="absolute -inset-0.5" />
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <div
          class="flex flex-1 items-center sm:items-stretch sm:ml-0 ml-4 justify-start"
        >
          <div class="flex flex-shrink-0 items-center">
            <img class="h-4 mr-5 w-auto" src="/images/logo.svg" alt="Snap" />
          </div>
          <div class="hidden sm:ml-6 sm:block">
            <div class="flex space-x-4">
              <Menu as="div" class="relative text-left">
                <MenuButton
                  v-on:click="toggleDropdownFeatures"
                  :class="{ 'text-black': showDropdownFeatures }"
                  class="inline-flex w-full justify-center rounded-m px-4 py-2 text-sm font-medium text-gray-500 hover:text-black"
                >
                  Features
                  <ChevronDownIcon
                    :class="{ 'rotate-180 text-black': showDropdownFeatures }"
                    class="ml-2 -mr-1 h-5 w-5 transition-transform transform text-gray-500 hover:text-black"
                    aria-hidden="true"
                  />
                </MenuButton>

                <transition
                  enter-active-class="transition duration-100 ease-out"
                  enter-from-class="transform scale-95 opacity-0"
                  enter-to-class="transform scale-100 opacity-100"
                  leave-active-class="transition duration-75 ease-in"
                  leave-from-class="transform scale-100 opacity-100"
                  leave-to-class="transform scale-95 opacity-0"
                >
                  <MenuItems
                    class="absolute right-0 mt-2 w-56 origin-top-right rounded-lg bg-white shadow-lg"
                  >
                    <div class="px-1 py-1">
                      <MenuItem
                        v-for="(feature, index) in features"
                        :key="index"
                      >
                        <button
                          class="group flex w-full items-center rounded-md px-2 py-2 text-sm"
                        >
                          <img class="mx-5" :src="feature.img" />
                          <p class="font-thin text-gray-600">
                            {{ feature.name }}
                          </p>
                        </button>
                      </MenuItem>
                    </div>
                  </MenuItems>
                </transition>
              </Menu>
              <Menu as="div" class="relative text-left">
                <MenuButton
                  v-on:click="toggleDropdownCompany"
                  :class="{ 'text-black': showDropdownCompany }"
                  class="inline-flex w-full justify-center rounded-m px-4 py-2 text-sm font-medium text-gray-500 hover:text-black"
                >
                  Company
                  <ChevronDownIcon
                    :class="{ 'rotate-180 text-black': showDropdownCompany }"
                    class="ml-2 -mr-1 h-5 w-5 transition-transform transform text-gray-500 hover:text-black"
                    aria-hidden="true"
                  />
                </MenuButton>

                <transition
                  enter-active-class="transition duration-100 ease-out"
                  enter-from-class="transform scale-95 opacity-0"
                  enter-to-class="transform scale-100 opacity-100"
                  leave-active-class="transition duration-75 ease-in"
                  leave-from-class="transform scale-100 opacity-100"
                  leave-to-class="transform scale-95 opacity-0"
                >
                  <MenuItems
                    class="absolute right-0 mt-2 w-32 origin-top-right rounded-lg bg-white shadow-lg"
                  >
                    <div class="px-1 py-1">
                      <MenuItem>
                        <button
                          class="group flex w-full items-center rounded-md px-2 py-2 text-sm"
                        >
                          <p class="font-thin text-gray-600">History</p>
                        </button>
                      </MenuItem>
                      <MenuItem>
                        <button
                          class="group flex w-full items-center rounded-md px-2 py-2 text-sm"
                        >
                          <p class="font-thin text-gray-600">Our Team</p>
                        </button>
                      </MenuItem>
                      <MenuItem>
                        <button
                          class="group flex w-full items-center rounded-md px-2 py-2 text-sm"
                        >
                          <p class="font-thin text-gray-600">Blog</p>
                        </button>
                      </MenuItem>
                    </div>
                  </MenuItems>
                </transition>
              </Menu>
              <div
                class="relative text-left w-full items-center rounded-md px-2 py-2 text-sm cursor-pointer"
              >
                <p class="font-thin text-gray-600 hover:text-black">Careers</p>
              </div>
              <div
                class="relative text-left w-full items-center rounded-md px-2 py-2 text-sm cursor-pointer"
              >
                <p class="font-thin text-gray-600 hover:text-black">About</p>
              </div>
            </div>
          </div>
        </div>
        <div
          class="absolute inset-y-0 right-0 sm:flex hidden items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
        >
          <button
            type="button"
            class="font-thin bg-transparent p-5 mr-5 text-gray-500 hover:text-black"
          >
            Login
          </button>
          <button
            type="button"
            class="font-thin border border-grey-500 rounded-lg bg-transparent p-4 text-gray-500 hover:text-black hover:border-black"
          >
            Register
          </button>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="relative space-y-1 px-2 pb-3 pt-2">
        <DisclosureButton
          v-for="item in navigation"
          :key="item.name"
          as="a"
          :href="item.href"
          :class="[
            item.current
              ? 'bg-gray-900 text-white'
              : 'text-gray-300 hover:bg-gray-700 hover:text-white',
            'block rounded-md px-3 py-2 text-base font-medium',
          ]"
          :aria-current="item.current ? 'page' : undefined"
          >{{ item.name }}</DisclosureButton
        >
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<style></style>

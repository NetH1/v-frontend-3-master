<template>
  <div class="mt-24 container mx-auto w-full">
    <!-- <div v-for="(p, id) in cart" :key="p.id">
        <div class="flex justify-between  h-full">
            <div class="w-1/4">
                <img :src="'http://38.242.229.113:8055/assets/' + p.image.id" alt="">
      <button
        @click="deleteFromCart(id)"
        class="border-2 border-black p-1 hover:text-white hover:bg-black"
      >
        delete from cart
      </button>
      <div><p>{{p.title}}</p></div>
            </div>
        </div>
    </div> -->
    <!-- component -->
<div v-for="(p, id) in cart" :key="p.id">
  <div class="flex justify-center my-6">
  <div class="flex flex-col w-full p-8 text-gray-800 bg-white shadow-lg pin-r pin-y md:w-4/5 lg:w-4/5">
    <div class="flex-1">
      <table class="w-full text-sm lg:text-base" cellspacing="0">
        <thead>
          <tr class="h-12 uppercase">
            <th class="hidden md:table-cell"></th>
            <th class="text-left">Product</th>
            <th class="lg:text-right text-left pl-5 lg:pl-0">
              <span class="lg:hidden" title="Quantity">Qtd</span>
              <span class="hidden lg:inline">Quantity</span>
            </th>
            <th class="hidden text-right md:table-cell">Unit price</th>
            <th class="text-right">Total price</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="hidden pb-4 md:table-cell">
              <a href="#">
                <img :src="'http://38.242.229.113:8055/assets/' + p.image.id" class="w-36 rounded" alt="Thumbnail">
              </a>
            </td>
            <td>
              <a href="#">
                <p class="mb-2 md:ml-4 ">{{p.title}}</p>
                <form action="" >
                  <button @click="deleteFromCart(id)" class="text-gray-700 md:ml-4">
                    <small>(Remove item)</small>
                  </button>
                </form>
              </a>
            </td>
            <td class="justify-center md:justify-end md:flex mt-6">
              <div class="w-20 h-10">
                <div class="relative flex flex-row w-full h-8">
                <input type="number" value="1" 
                  class="w-full font-semibold text-center text-gray-700 bg-gray-200 outline-none focus:outline-none hover:text-black focus:text-black" />
                </div>
              </div>
            </td>
            <td class="hidden text-right md:table-cell">
              <span class="text-sm lg:text-base font-medium">
                {{p.price}}$
              </span>
            </td>
            <td class="text-right">
              <span class="text-sm lg:text-base font-medium">
                {{p.price}}$
              </span>
            </td>
          </tr> 
        </tbody>
      </table>
    </div>
  </div>
</div>
</div>
<div class="mt-14 font-medium text-lg font-serif">Total all products:</div>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';
import { deleteFromCart } from '../utils/cart'
export default {
  setup() {
    const cart = JSON.parse(sessionStorage.getItem('cart'));
    return {
      cart,
      deleteFromCart
    }
  },
};
</script>

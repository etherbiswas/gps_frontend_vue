<script setup>
  import { useDataStore } from '../store'

  const store = useDataStore()
  const devices = store.devices
</script>

<template>

    <table class="min-w-full">            
        <thead>              
            <tr>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50">
                  Name
                </th>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50" >
                  Active State
                </th>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50" >
                  Drive Status
                </th>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50" >
                  Speed
                </th>
            </tr>
        </thead>

        <tbody class="bg-white">
            <tr v-for="device in devices" :key="device.device_id">
                <td
                  class="px-6 py-4 text-sm font-medium leading-5 text-gray-900 border-b border-gray-200 whitespace-nowrap"
                >
                  {{ device.display_name }}
                </td>

                <td
                  class="px-6 py-4 border-b border-gray-200 whitespace-nowrap"
                >
                  <span
                    class="inline-flex px-2 text-xs font-semibold leading-5 text-green-800 bg-green-100 rounded-full"
                  >{{ device.active_state }}</span>
                </td>

                <td
                  class="px-6 py-4 text-sm font-medium leading-5 text-gray-900 border-b border-gray-200 whitespace-nowrap"
                >
                  {{ device.drive_status }}
                </td>

                <td
                  class="px-6 py-4 text-sm font-medium leading-5 text-gray-900 border-b border-gray-200 whitespace-nowrap"
                >
                  {{ device.speed }}
              </td>
            </tr>
        </tbody>
    </table>

</template>
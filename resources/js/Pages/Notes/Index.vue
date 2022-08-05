<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
</script>

<template>
    <AppLayout title="Dashboard">
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
              Notes
            </h2>
        </template>

        <div class="py-12">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
                <div class="overflow-hidden bg-white shadow-xl sm:rounded-lg">

                <tbody>
                                <tr
                                v-for="note in notes">
                                    <td class="px-4 py-2 border">
                                        {{ note.excerpt }}
                                    </td>
                                    <td class="px-4 py-2">

                                        <inertia-link :href="route('notes.show', note.id)">
                                            Ver
                                        </inertia-link>
                                    </td>
                                    <td class="px-4 py-2">
                                        <inertia-link :href="route('notes.edit', note.id)">
                                            Editar
                                        </inertia-link>
                                    </td>
                                </tr>
                        </tbody>
                </div>
            </div>
        </div>
    </AppLayout>
</template>
<script>

    export default {
        components: {
            AppLayout,
        },
        props: {
            notes: Array,
        }
    }
</script>

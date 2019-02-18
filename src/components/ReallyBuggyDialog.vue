<template>
    <ul>
        <li v-for="item in items" :key="item.id">
            {{ item.id }} - {{ item.text }}

            <v-btn @click="open = true" icon color="red">
                <v-icon>delete_forever</v-icon>
            </v-btn>

            <v-dialog persistent :value="open">
                <v-card>
                    <v-card-title class="headline">
                        Delete item with ID from context: {{item.id}}?
                    </v-card-title>

                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn @click="open = false" color="grey-lighten-2">No</v-btn>
                        <v-btn @click="remove(item.id)" color="warning">Yes, but dangerous</v-btn>
                    </v-card-actions>
                </v-card>
            </v-dialog>
        </li>
    </ul>
</template>

<script>
    /* eslint-disable */

    export default {
        methods: {
            remove(id) {
                // Hold your horses! Can't trust this ID to be correct!!!!
            }
        },
        data() {
            return {
                open: false,
                items: [
                    {
                        id: 1,
                        text: 'Item 1'
                    },
                    {
                        id: 2,
                        text: 'Item 2'
                    },
                    {
                        id: 3,
                        text: 'Item 3'
                    }
                ]
            }
        }
    }
</script>
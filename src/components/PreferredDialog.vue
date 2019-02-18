<template>
    <ul>
        <li v-for="item in items" :key="item.id">
            {{ item.id }} - {{ item.text }}

            <v-btn @click="prepareDelete(item.id)" icon color="red">
                <v-icon>delete_forever</v-icon>
            </v-btn>
        </li>

        <v-dialog persistent :value="dialogId">
            <v-card>
                <v-card-title class="headline">
                    Delete item with ID {{dialogId}}?
                </v-card-title>

                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn @click="dialogId = false" color="grey-lighten-2">No</v-btn>
                    <v-btn @click="remove(dialogId)" color="green">Yes</v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>

    </ul>
</template>

<script>
    /* eslint-disable */

    export default {
        methods: {
            prepareDelete(id) {
                this.dialogId = id;
            },
            remove(id) {
                // Hold your horses! Can't trust this ID to be correct!!!!
            }
        },
        data() {
            return {
                dialogId: false,
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
<template>
    <ul>
        <li v-for="item in items" :key="item.id">
            {{ item.id }} - {{ item.text }}

            <v-btn @click="prepareDelete(item.id)" icon color="red">
                <v-icon>delete_forever</v-icon>
            </v-btn>

            <v-dialog persistent :value="dialogId">
                <v-card>
                    <v-card-title v-if="dialogId === item.id" class="headline">
                        Delete item with ID from context: {{item.id}}?
                    </v-card-title>

                    <v-card-title v-if="dialogId !== item.id" class="headline">
                        Oops.. IDs are not equal! Input to dialog: {{dialogId}}, ID from context: {{item.id}}?
                    </v-card-title>

                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn @click="dialogId = false" color="grey-lighten-2">No</v-btn>
                        <v-btn @click="remove(dialogId)" color="green">Yes</v-btn>
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
<template>
    <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">本のタイトル</v-list-item-title>

            <v-row>
                <v-col cols="1" md="1">
                <v-text-field v-model="zaiko" label='zaiko'></v-text-field>
                </v-col>
                <v-col cols="1" md="1">
                <v-text-field v-model="zaiko" label='zaiko'></v-text-field>
                </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar tile size="80" color="grey" ></v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text v-on:click="zaiko -+ 1">売</v-btn>
            <v-btn text>戻</v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
  data: () => ({
    uriage: 0,
    zaiko: 100
  }),
};
</script>
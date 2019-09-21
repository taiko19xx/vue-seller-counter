<template>
  <v-app>
    <v-content>
      <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">GCPで手軽にはじめる！ハニーポットの構築と分析(セット)</v-list-item-title>

            <v-row>
              <v-col>
                <v-text-field v-model.number="books.book1.uriage" label="売上" type="number"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field v-model.number="books.book1.zaiko"  label="在庫" type="number"></v-text-field>
              </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar size="160">
              <v-img src="@/assets/book1.png" />
            </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text @click="add($event, 'book1')">売</v-btn>
            <v-btn text @click="minus($event, 'book1')">戻</v-btn>
        </v-card-actions>
      </v-card>

      <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">GCPで手軽にはじめる！ハニーポットの構築と分析(DLのみ)</v-list-item-title>

            <v-row>
              <v-col>
                <v-text-field v-model.number="books.book2.uriage" label="売上" type="number"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field v-model.number="books.book2.zaiko"  label="在庫" type="number"></v-text-field>
              </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar size="160">
              <v-img src="@/assets/book1.png" />
            </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text @click="add($event, 'book2')">売</v-btn>
            <v-btn text @click="minus($event, 'book2')">戻</v-btn>
        </v-card-actions>
      </v-card>

      <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">PHPでもサーバーレス！AWS Lambda Custom Runtime入門</v-list-item-title>

            <v-row>
              <v-col>
                <v-text-field v-model.number="books.book3.uriage" label="売上" type="number"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field v-model.number="books.book3.zaiko"  label="在庫" type="number"></v-text-field>
              </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar size="160">
              <v-img src="@/assets/book3.png" />
            </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text @click="add($event, 'book3')">売</v-btn>
            <v-btn text @click="minus($event, 'book3')">戻</v-btn>
        </v-card-actions>
      </v-card>

      <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">PHPでゼロからはじめるAWS Lambda Custom Runtime</v-list-item-title>

            <v-row>
              <v-col>
                <v-text-field v-model.number="books.book4.uriage" label="売上" type="number"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field v-model.number="books.book4.zaiko"  label="在庫" type="number"></v-text-field>
              </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar size="160">
              <v-img src="@/assets/book4.png" />
            </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text @click="add($event, 'book4')">売</v-btn>
            <v-btn text @click="minus($event, 'book4')">戻</v-btn>
        </v-card-actions>
      </v-card>

      <v-card class="mx-auto md-5" outlined>
        <v-list-item three-line>
            <v-list-item-content>
            <v-list-item-title class="headline mb-1">Raspberry Pi+AWS IoTでGPSロガーをつくろう</v-list-item-title>

            <v-row>
              <v-col>
                <v-text-field v-model.number="books.book5.uriage" label="売上" type="number"></v-text-field>
              </v-col>
              <v-col>
                <v-text-field v-model.number="books.book5.zaiko"  label="在庫" type="number"></v-text-field>
              </v-col>
            </v-row>

            </v-list-item-content>
            <v-list-item-avatar size="160">
              <v-img src="@/assets/book5.png" />
            </v-list-item-avatar>
        </v-list-item>

        <v-card-actions>
            <v-btn text @click="add($event, 'book5')">売</v-btn>
            <v-btn text @click="minus($event, 'book5')">戻</v-btn>
        </v-card-actions>
      </v-card>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    books: {
      book1: {
        zaiko: 0,
        uriage: 0
      },
      book2: {
        zaiko: 0,
        uriage: 0
      },
      book3: {
        zaiko: 0,
        uriage: 0
      },
      book4: {
        zaiko: 0,
        uriage: 0
      },
      book5: {
        zaiko: 0,
        uriage: 0
      }
    }
  }),
  mounted() {
    if (localStorage.getItem('books')) {
      try {
        this.books = JSON.parse(localStorage.getItem('books'));
      } catch(e) {
        localStorage.removeItem('books');
      }
    }
  },
  methods: {
    add(event, targetBook) {
      this.books[targetBook].uriage += 1;
      this.books[targetBook].zaiko -= 1;

      this.saveCount();
    },
    minus(event, targetBook) {
      this.books[targetBook].uriage -= 1;
      this.books[targetBook].zaiko += 1;

      this.saveCount();
    },
    saveCount() {
      const parsed = JSON.stringify(this.books);
      localStorage.setItem('books', parsed);
    }
  }
};
</script>

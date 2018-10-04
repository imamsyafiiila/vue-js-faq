<template>
    <div>
      <br>
      <div class="row" style="margin-left: 5px">
        <div class="col-lg-3"></div>
        <div class="col-lg-6">
          Cari FAQ: <input type="text" v-model="search" name="" value="" placeholder="Search Faqs">
        </div>
        <div class="col-lg-3"></div>
      </div>
      <section class="cd-faq">
      	<ul class="cd-faq-categories">
          <li v-for="faq in reloadFaqs"><a v-bind:href="'#' + faq.title">{{ faq.title }}</a></li>
      	</ul> <!-- cd-faq-categories -->

      	<div class="cd-faq-items">
          <ul v-bind:id="faq.title" v-for="faq in reloadFaqs" class="cd-faq-group">
      			<li class="cd-faq-title"><h2>{{ faq.title }}</h2></li>
            <li v-for="qna in faq.question_answer" v-bind:class="classOpen">
      				<a class="cd-faq-trigger" href="#0">
      					<div v-html="qna.question"></div>
              </a>
      				<div class="cd-faq-content" v-bind:style="defaultToggle">
      					<div v-html="qna.answer"></div>
      				</div>
            </li>
          </ul>
      	</div> <!-- cd-faq-items -->
      	<a href="#0" class="cd-close-panel">Close</a>
      </section> <!-- cd-faq -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      faqs: [
          {
              "id": 1,
              "title": "Shipping",
              "type": "com",
              "sort": "1.00",
              "is_active": 1,
              "created_at": "2018-09-27 15:03:17",
              "updated_at": "2018-09-27 15:03:17",
              "deleted_at": null,
              "question_answer": [
                  {
                      "id": 1,
                      "faq_category_id": 1,
                      "question": "Apa itu shipping?",
                      "answer": "<p>Shipping adalah</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 15:03:53",
                      "updated_at": "2018-09-27 15:03:53",
                      "deleted_at": null
                  },
                  {
                      "id": 2,
                      "faq_category_id": 1,
                      "question": "Apa itu IT?",
                      "answer": "<p>IT adalah</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 15:16:59",
                      "updated_at": "2018-09-27 15:16:59",
                      "deleted_at": null
                  }
              ]
          },
          {
              "id": 2,
              "title": "Penjualanan",
              "type": "com",
              "sort": "2.00",
              "is_active": 1,
              "created_at": "2018-09-27 16:26:54",
              "updated_at": "2018-09-27 16:26:54",
              "deleted_at": null,
              "question_answer": [
                  {
                      "id": 3,
                      "faq_category_id": 2,
                      "question": "Apa itu penjualan?",
                      "answer": "<p>Penjualan adalah change</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:27:18",
                      "updated_at": "2018-09-27 16:27:18",
                      "deleted_at": null
                  },
                  {
                      "id": 4,
                      "faq_category_id": 2,
                      "question": "How do I change my password?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae quidem blanditiis delectus corporis, possimus officia sint sequi ex tenetur id impedit est pariatur iure animi non a ratione reiciendis nihil sed consequatur atque repellendus fugit perspiciatis rerum et. Dolorum consequuntur fugit deleniti, soluta fuga nobis. Ducimus blanditiis velit sit iste delectus obcaecati debitis omnis, assumenda accusamus cumque perferendis eos aut quidem! Aut, totam rerum, cupiditate quae aperiam voluptas rem inventore quas, ex maxime culpa nam soluta labore at amet nihil laborum? Explicabo numquam, sit fugit, voluptatem autem atque quis quam voluptate fugiat earum rem hic, reprehenderit quaerat tempore at. Aperiam.</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:34:59",
                      "updated_at": "2018-09-27 16:34:59",
                      "deleted_at": null
                  },
                  {
                      "id": 5,
                      "faq_category_id": 2,
                      "question": "How do I sign up?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi cupiditate et laudantium esse adipisci consequatur modi possimus accusantium vero atque excepturi nobis in doloremque repudiandae soluta non minus dolore voluptatem enim reiciendis officia voluptates, fuga ullam? Voluptas reiciendis cumque molestiae unde numquam similique quas doloremque non, perferendis doloribus necessitatibus itaque dolorem quam officia atque perspiciatis dolore laudantium dolor voluptatem eligendi? Aliquam nulla unde voluptatum molestiae, eos fugit ullam, consequuntur, saepe voluptas quaerat deleniti. Repellendus magni sint temporibus, accusantium rem commodi?</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:35:35",
                      "updated_at": "2018-09-27 16:35:35",
                      "deleted_at": null
                  },
                  {
                      "id": 6,
                      "faq_category_id": 2,
                      "question": "Apa itu penjualan?",
                      "answer": "<p>Penjualan adalah</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:27:18",
                      "updated_at": "2018-09-27 16:27:18",
                      "deleted_at": null
                  }
              ]
          },
          {
              "id": 3,
              "title": "CS",
              "type": "com",
              "sort": "2.00",
              "is_active": 1,
              "created_at": "2018-09-27 16:26:54",
              "updated_at": "2018-09-27 16:26:54",
              "deleted_at": null,
              "question_answer": [
                  {
                      "id": 8,
                      "faq_category_id": 3,
                      "question": "How do I sign up?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi cupiditate et laudantium esse adipisci consequatur modi possimus accusantium vero atque excepturi nobis in doloremque repudiandae soluta non minus dolore voluptatem enim reiciendis officia voluptates, fuga ullam? Voluptas reiciendis cumque molestiae unde numquam similique quas doloremque non, perferendis doloribus necessitatibus itaque dolorem quam officia atque perspiciatis dolore laudantium dolor voluptatem eligendi? Aliquam nulla unde voluptatum molestiae, eos fugit ullam, consequuntur, saepe voluptas quaerat deleniti. Repellendus magni sint temporibus, accusantium rem commodi?</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:35:35",
                      "updated_at": "2018-09-27 16:35:35",
                      "deleted_at": null
                  },
                  {
                      "id": 9,
                      "faq_category_id": 3,
                      "question": "How do I change my password?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae quidem blanditiis delectus corporis, possimus officia sint sequi ex tenetur id impedit est pariatur iure animi non a ratione reiciendis nihil sed consequatur atque repellendus fugit perspiciatis rerum et. Dolorum consequuntur fugit deleniti, soluta fuga nobis. Ducimus blanditiis velit sit iste delectus obcaecati debitis omnis, assumenda accusamus cumque perferendis eos aut quidem! Aut, totam rerum, cupiditate quae aperiam voluptas rem inventore quas, ex maxime culpa nam soluta labore at amet nihil laborum? Explicabo numquam, sit fugit, voluptatem autem atque quis quam voluptate fugiat earum rem hic, reprehenderit quaerat tempore at. Aperiam.</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:34:59",
                      "updated_at": "2018-09-27 16:34:59",
                      "deleted_at": null
                  },
                  {
                      "id": 10,
                      "faq_category_id": 3,
                      "question": "How do I sign up?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi cupiditate et laudantium esse adipisci consequatur modi possimus accusantium vero atque excepturi nobis in doloremque repudiandae soluta non minus dolore voluptatem enim reiciendis officia voluptates, fuga ullam? Voluptas reiciendis cumque molestiae unde numquam similique quas doloremque non, perferendis doloribus necessitatibus itaque dolorem quam officia atque perspiciatis dolore laudantium dolor voluptatem eligendi? Aliquam nulla unde voluptatum molestiae, eos fugit ullam, consequuntur, saepe voluptas quaerat deleniti. Repellendus magni sint temporibus, accusantium rem commodi?</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:35:35",
                      "updated_at": "2018-09-27 16:35:35",
                      "deleted_at": null
                  },
                  {
                      "id": 11,
                      "faq_category_id": 3,
                      "question": "Apa itu penjualan?",
                      "answer": "<p>Penjualan adalah  sesuatu yang </p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:27:18",
                      "updated_at": "2018-09-27 16:27:18",
                      "deleted_at": null
                  },
                  {
                      "id": 12,
                      "faq_category_id": 3,
                      "question": "How do I change my password?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quae quidem blanditiis delectus corporis, possimus officia sint sequi ex tenetur id impedit est pariatur iure animi non a ratione reiciendis nihil sed consequatur atque repellendus fugit perspiciatis rerum et. Dolorum consequuntur fugit deleniti, soluta fuga nobis. Ducimus blanditiis velit sit iste delectus obcaecati debitis omnis, assumenda accusamus cumque perferendis eos aut quidem! Aut, totam rerum, cupiditate quae aperiam voluptas rem inventore quas, ex maxime culpa nam soluta labore at amet nihil laborum? Explicabo numquam, sit fugit, voluptatem autem atque quis quam voluptate fugiat earum rem hic, reprehenderit quaerat tempore at. Aperiam.</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:34:59",
                      "updated_at": "2018-09-27 16:34:59",
                      "deleted_at": null
                  },
                  {
                      "id": 13,
                      "faq_category_id": 3,
                      "question": "How do I sign up?",
                      "answer": "<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quasi cupiditate et laudantium esse adipisci consequatur modi possimus accusantium vero atque excepturi nobis in doloremque repudiandae soluta non minus dolore voluptatem enim reiciendis officia voluptates, fuga ullam? Voluptas reiciendis cumque molestiae unde numquam similique quas doloremque non, perferendis doloribus necessitatibus itaque dolorem quam officia atque perspiciatis dolore laudantium dolor voluptatem eligendi? Aliquam nulla unde voluptatum molestiae, eos fugit ullam, consequuntur, saepe voluptas quaerat deleniti. Repellendus magni sint temporibus, accusantium rem commodi?</p>",
                      "is_active": 1,
                      "created_at": "2018-09-27 16:35:35",
                      "updated_at": "2018-09-27 16:35:35",
                      "deleted_at": null
                  }
              ]
          }
      ],
      selected: true,
      search: '',
      defaultToggle: 'display: none',
      classOpen: ''
    }
  },
  computed: {
    reloadFaqs: function() {
      var finalFaqs = [];
      var searchLow = this.search;
      // clear
      this.faqs.forEach(function(faq) {
        var qna = faq.question_answer;
        qna.forEach(function(value) {
          var question = value.question;
          question = question.replace('<span class="highlight">', '');
          question = question.replace("</span>", "");
          value.question = question;
          var answer = value.answer;
          answer = answer.replace('<span class="highlight">', '');
          answer = answer.replace("</span>", "");
          value.answer = answer;
        });
      });

      searchLow = searchLow.toLowerCase();
      if (searchLow) {
        this.faqs.forEach(function(faq, key) {
          var qna = faq.question_answer;
          var qnaMatch = [];
          qna.forEach(function(value, keyQna) {
            var answerLow = value.answer;
            answerLow = answerLow.toLowerCase();
            var questionLow = value.question;
            questionLow = questionLow.toLowerCase();
            if (searchLow) {
              if (questionLow.match(searchLow)) {
                var questionNew = value.question;
                questionNew = questionNew.toLowerCase();
                questionNew = questionNew.replace(searchLow, '<span class="highlight">' + searchLow + '</span>');
                value.question = questionNew;
                qnaMatch.push(value);
              } else if (answerLow.match(searchLow)) {
                var answerNew = value.answer;
                answerNew = answerNew.toLowerCase();
                answerNew = answerNew.replace(searchLow, '<span class="highlight">' + searchLow + '</span>');
                value.answer = answerNew;
                qnaMatch.push(value);
              }
            }
          });
          if (qnaMatch.length != 0) {
            finalFaqs.push({"title": faq.title, "question_answer" : qnaMatch});
          }
        });
        if (finalFaqs.length != 0) {
          this.defaultToggle = 'display: block';
          this.classOpen = 'content-visible';
          return finalFaqs;
        } else {
          this.defaultToggle = 'display: none';
          this.classOpen = '';
          return this.faqs;
        }
      } else {
        this.defaultToggle = 'display: none';
        this.classOpen = '';
        return this.faqs;
      }
    }
  }
}
</script>

<style>

.highlight{
  background-color: yellow;
  font-style: italic;
}
</style>

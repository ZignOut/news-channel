<template>
  <v-container>
    <search-bar :searchKeys="news" @search="search"></search-bar>

    <news-post-group :allNews="news"></news-post-group>

    <v-fab-transition>
      <v-tooltip left>
        <template v-slot:activator="{ on }">
          <v-btn
            v-on="on"
            color="green darken-1"
            class="ma-md-12"
            fab
            dark
            absolute
            bottom
            right
            fixed
            href="/writePost"
          >
            <v-icon>mdi-plus</v-icon>
          </v-btn>
        </template>
        <span class="content">Write Post</span>
      </v-tooltip>
    </v-fab-transition>
  </v-container>
</template>

<script>
import searchBarVue from "../components/searchBar.vue";
import newsPostGroupVue from "../components/newsPostGroup.vue";
// import tabTestVue from '../components/tabTest.vue';

export default {
  name: "Home",

  components: {
    "search-bar": searchBarVue,
    "news-post-group": newsPostGroupVue
    // "tab-test": tabTestVue
  },

  data() {
    return {
      news: [
        {
          category: "Cele",
          posts: [
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93015194_516910148994335_6257164753475469312_n.jpg?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeHmWY9boix3W4pzDfuTU_yDM6Bl5O1mQHEzoGXk7WZAceW9n6cGY5gh4E4yRv-FoiWng_y1tHN8vUliZCIDi1F_&_nc_ohc=CzWM_LAi3egAX9eNjmi&_nc_ht=scontent.frgn5-2.fna&oh=94e5de10481e64cb4f1000d4e05f026f&oe=5EBAF509",
              title: "ထင်အောင်ခန့်စော်ရသွားပီလား??",
              date: "ဖေ၊ ၃၀၊ ၂၀၂၀",
              shortText:
                "ထင်အောင်ခန့် စော်ရသွားလေပီ ဆိုသောသီတင်းမှာ သီတင်းမှားသာဖြစ်ကြောင်း မအူပင်ကွန်ပျူတာတက္ကသိုလ်မှ ပြောရေးဆိုခွင့်ရှိသူ ခန့်ညီအောင်(ခ)အုပ်ကြီးမှ ပြောကြားပါတယ်။ ယခုအချိန်မှာတော့ သီတင်းမှားဖြန့်ဝေသူ ကိုကောင်းမြတ်ပိုင်ကို တောင်ဥက္ကလာမြို့မရဲစခန်းမှာ ဖမ်းဆီးထိန်းသိမ်းထားပီး တရားဥပဒေအရ အရေးယူသွားမည်ဖြစ်ကြောင်း တောင်ဥက္ကလာမြို့မရဲစခန်း စခန်းမှူး ကိုအဝတ်စုတ်မှ ကျွန်တော်တို့ စောက်ချောကြီး media ကိုဖြေကြားခဲ့ပါတယ်။"
            },
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/91694065_238494333866485_3181949288863236096_n.jpg?_nc_cat=108&_nc_sid=b96e70&_nc_eui2=AeFmBrRvdkDJgszTorn7n-HQLiD_v_h_ZRguIP-_-H9lGDYAjppQy-w4JUhHHVhlLakSgMFInqMY7YCiRVZGhQdT&_nc_ohc=HW_tPi0uPL4AX8YcQda&_nc_ht=scontent.frgn5-2.fna&oh=8001c7417a1e924fe2fbb06f825392db&oe=5EBB198E",
              title: "ပဲမြစ်ကိစ္စ ဖိုးညီရှင်းပီ",
              date: "ဇန်၊ ၂၁၊ ၂၀၂၀",
              shortText:
                "ယခင်ကွန်ပျူတာတက္ကသိုလ်(မအူပင်) ပါမောက္ခချုပ်ဖလား ချန်ပီယံဟောင်း ထွန်းထက်အောင်(ခ)ကိုဖိုးညီသည် လတ်တလော လူမှုကွန်ယက်ပေါ်မှာ မဖွယ်မယာပုံများ ပျံ့နှံ့နေပီး ပရိတ်သတ်အများရဲ့ 'ပဲမြစ်' ဟုပြောဆိုတိုက်ခိုက်ခြင်းကို ခံနေရသူဖြစ်ပါတယ်။ အဆိုပါ ကိစ္စရပ်နှင့်စပ်လျဥ်းပီး ကိုဖိုးညီကို မေးမြန်းရာမှာတော့ ယခုပျံ့နှံ့နေသော ပုံများမှ မိမိနှင့်မဆိုင်ကြောင်း မိမိမဟုတ်ကြောင်း၊ မယုံလျှင် နာရိစင်တဝိုက်တွင်မေးကြည့်နိုင်ကြောင်း၊ ယခုကိစ္စ စတင်ဖြန့်ဝေသူအား တရားဥပဒေအရ အရေးယူသွားမှာဖြစ်ကြောင်း ပြောကြားခဲ့ပါတယ်။"
            },
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/89436699_292038978435535_5010837842008473600_n.jpg?_nc_cat=105&_nc_sid=b96e70&_nc_ohc=ntovbeKiZ1UAX95wvIY&_nc_ht=scontent.frgn5-2.fna&oh=bf9a1d8a0cbe945491943549d4f5f4b6&oe=5EBCA949",
              title:
                "ဖန်များ၏ခင်တွယ်မှုကို ခံယူနေရတဲ့ underground raperလေး ကို wizard",
              date: "ဇန်၊ ၂၁၊ ၂၀၂၀",
              shortText:
                "မကြာသေးမှီက နှုတ်ခမ်းနီမလေးများကြား ရေပန်းစားလာသည့် UG အဆိုတော်လေး ကို wizard သည် သူ့ရဲ့အသစ်ထွက်ရှိလာတဲ့ album ကြောင့်ပရိတ်သတ်အများ၏ချစ်ခင်မှုကို ပိုရလာခဲ့သူတစ်ဦးလည်းဖြစ်ပါတယ်။ ဒီထက်မက ပိုပီးစိတ်ဝင်စားဖို့ကောင်းတဲ့ တစ်ချက်ကတော့ ကမ္ဘာကျော်အနုပညာရှင် 'Justin Beber' ဖန်များကို 'Believers' ဟုတင်စားသုံးနှုံးကြသလိုပဲ ကို အဝတ်စရဲ့ ဖန်များကိုလဲ အဝတ်စုတ်များချစ်စနိုးနဲ့ ခေါ်ကြတာပဲဖြစ်ပါတယ်။ အဝတ်စုတ်များက ကိုအဝတ်စကို ချစ်ခင်ကြသလိုပဲ ကိုအဝတ်စအနေနဲ့ကလဲ မိမိကိုအားပေးကြသော ဖန်များရှိတာ အလွန်ဝမ်းသာပါကြောင်း ကျေးဇူးလဲတင်ပါကြောင်း နောင်ဒီထက်ပိုပီးကြိုးစားသွားမည်ဖြစ်ပါကြောင်း ဖန်များကိုလဲတဖန်ပြန်ခင်ပါကြောင်း ယနေ့ခောတ် media ရဲ့ interview တစ်ခုမှာပြောကြားသွားခဲ့တာပဲဖြစ်ပါတယ်။"
            },
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93365962_1016971462033935_4845840879421751296_n.jpg?_nc_cat=111&_nc_sid=b96e70&_nc_ohc=8ZDxosMYTXgAX9-NaJ5&_nc_ht=scontent.frgn5-2.fna&oh=5d52827193b576d95305d451409ffd56&oe=5EC0FC1C",
              title:
                "တစ်နှစ်ထက် တစ်နှစ်ပိုမှေးမှိန်လာတဲ့ ဇိမ်မယ်ဈေးကွက်",
              date: "ဖေ၊ ၂၀၊ ၂၀၂၀",
              shortText:
                "မြန်မာနိုင်ငံဟာဆိုရင်တော့ အရပ်သားအစိုးရသက်တမ်းဟာ ဆယ်စုနှစ်တစ်ခုသာသာရှိသေးပီး၊ အတွေ့အကြုံနုလှတဲ့ အစိုးရကတော့ စိန်ခေါ်မှုများစွာနဲ့ ရင်ဆိုင်နေရဆဲဖြစ်ပါတယ်။ ဒီလိုစိန်ခေါ်မှုတွေအနက်မှာ မြန်မာပြည်ဇိမ်မယ်လောကလဲ အပါအဝင်ပဲဖြစ်ပါတယ်။ ဒီကိစ္စနဲ့ပက်သက်ပီးတော့ ကျွန်တော်တို့ ဗောက်ချီးစုံမီဒီယာမှ လှိုင်သာယာမီးခွက်ဈေးမှ ဇိမ်မယ်ကိုယ်စားလှယ် ကိုအောင်ကောင်းမြတ်(အမည်လွဲ) က'ဟုတ်တယ်ဗျ၊ တနှစ်ထက် တနှစ်ကတော့ ဖောက်သည်ကပိုပိုများလာတယ်။ အထူးသဖြင့်နိုင်ငံခြားသားတွေပေါ့၊ ကောင်မလေးတွေမနိုင်တော့တဲ့အခါ ကျတော်ပါဝင်ထိန်းရတာမျီုးတွေလဲရှိတယ်။ ဝမ်းရေးဆိုတော့လဲ နောက်တော့ကျင့်သားရသွားတာပါပဲ' ဟုဖြေကြားခဲ့ပါတယ်။ ကိုအောင်ကောင်းမြတ်(အမည်လွဲ)ဟာ ယခင်ဇိမ်မယ်များ မအားလပ်တဲ့အချိန်မျိူးတွင်သာ ဧည့်သည်များကိုဖျော်ဖြေပေးရင်း ယခုဆို လိင်တူဧည့်သည်များကြား ပါရိးဟုသောအမည်ဖြင့် ရေပန်းစားလာခဲ့တာဖြစ်ပါတယ်။"
            }
          ]
        },
        {
          category: "news",
          posts: [
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93015194_516910148994335_6257164753475469312_n.jpg?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeHmWY9boix3W4pzDfuTU_yDM6Bl5O1mQHEzoGXk7WZAceW9n6cGY5gh4E4yRv-FoiWng_y1tHN8vUliZCIDi1F_&_nc_ohc=CzWM_LAi3egAX9eNjmi&_nc_ht=scontent.frgn5-2.fna&oh=94e5de10481e64cb4f1000d4e05f026f&oe=5EBAF509",
              title: "ထင်အောင်ခန့်စော်ရသွားပီလား2??",
              date: "ဖေ၊ ၃၀၊ ၂၀၂၀",
              shortText:
                "ထင်အောင်ခန့် စော်ရသွားလေပီ ဆိုသောသီတင်းမှာ သီတင်းမှားသာဖြစ်ကြောင်း မအူပင်ကွန်ပျူတာတက္ကသိုလ်မှ ပြောရေးဆိုခွင့်ရှိသူ ခန့်ညီအောင်(ခ)အုပ်ကြီးမှ ပြောကြားပါတယ်။ ယခုအချိန်မှာတော့ သီတင်းမှားဖြန့်ဝေသူ ကိုကောင်းမြတ်ပိုင်ကို တောင်ဥက္ကလာမြို့မရဲစခန်းမှာ ဖမ်းဆီးထိန်းသိမ်းထားပီး တရားဥပဒေအရ အရေးယူသွားမည်ဖြစ်ကြောင်း တောင်ဥက္ကလာမြို့မရဲစခန်း စခန်းမှူး ကိုအဝတ်စုတ်မှ ကျွန်တော်တို့ စောက်ချောကြီး media ကိုဖြေကြားခဲ့ပါတယ်။"
            }
          ]
        },
        {
          category: "international",
          posts: [
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93015194_516910148994335_6257164753475469312_n.jpg?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeHmWY9boix3W4pzDfuTU_yDM6Bl5O1mQHEzoGXk7WZAceW9n6cGY5gh4E4yRv-FoiWng_y1tHN8vUliZCIDi1F_&_nc_ohc=CzWM_LAi3egAX9eNjmi&_nc_ht=scontent.frgn5-2.fna&oh=94e5de10481e64cb4f1000d4e05f026f&oe=5EBAF509",
              title: "ထင်အောင်ခန့်စော်ရသွားပီလား2??",
              date: "ဖေ၊ ၃၀၊ ၂၀၂၀",
              shortText:
                "ထင်အောင်ခန့် စော်ရသွားလေပီ ဆိုသောသီတင်းမှာ သီတင်းမှားသာဖြစ်ကြောင်း မအူပင်ကွန်ပျူတာတက္ကသိုလ်မှ ပြောရေးဆိုခွင့်ရှိသူ ခန့်ညီအောင်(ခ)အုပ်ကြီးမှ ပြောကြားပါတယ်။ ယခုအချိန်မှာတော့ သီတင်းမှားဖြန့်ဝေသူ ကိုကောင်းမြတ်ပိုင်ကို တောင်ဥက္ကလာမြို့မရဲစခန်းမှာ ဖမ်းဆီးထိန်းသိမ်းထားပီး တရားဥပဒေအရ အရေးယူသွားမည်ဖြစ်ကြောင်း တောင်ဥက္ကလာမြို့မရဲစခန်း စခန်းမှူး ကိုအဝတ်စုတ်မှ ကျွန်တော်တို့ စောက်ချောကြီး media ကိုဖြေကြားခဲ့ပါတယ်။"
            },
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93015194_516910148994335_6257164753475469312_n.jpg?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeHmWY9boix3W4pzDfuTU_yDM6Bl5O1mQHEzoGXk7WZAceW9n6cGY5gh4E4yRv-FoiWng_y1tHN8vUliZCIDi1F_&_nc_ohc=CzWM_LAi3egAX9eNjmi&_nc_ht=scontent.frgn5-2.fna&oh=94e5de10481e64cb4f1000d4e05f026f&oe=5EBAF509",
              title: "ထင်အောင်ခန့်စော်ရသွားပီလား2??",
              date: "ဖေ၊ ၃၀၊ ၂၀၂၀",
              shortText:
                "ထင်အောင်ခန့် စော်ရသွားလေပီ ဆိုသောသီတင်းမှာ သီတင်းမှားသာဖြစ်ကြောင်း မအူပင်ကွန်ပျူတာတက္ကသိုလ်မှ ပြောရေးဆိုခွင့်ရှိသူ ခန့်ညီအောင်(ခ)အုပ်ကြီးမှ ပြောကြားပါတယ်။ ယခုအချိန်မှာတော့ သီတင်းမှားဖြန့်ဝေသူ ကိုကောင်းမြတ်ပိုင်ကို တောင်ဥက္ကလာမြို့မရဲစခန်းမှာ ဖမ်းဆီးထိန်းသိမ်းထားပီး တရားဥပဒေအရ အရေးယူသွားမည်ဖြစ်ကြောင်း တောင်ဥက္ကလာမြို့မရဲစခန်း စခန်းမှူး ကိုအဝတ်စုတ်မှ ကျွန်တော်တို့ စောက်ချောကြီး media ကိုဖြေကြားခဲ့ပါတယ်။"
            },
            {
              imageLink:
                "https://scontent.frgn5-2.fna.fbcdn.net/v/t1.15752-9/93015194_516910148994335_6257164753475469312_n.jpg?_nc_cat=107&_nc_sid=b96e70&_nc_eui2=AeHmWY9boix3W4pzDfuTU_yDM6Bl5O1mQHEzoGXk7WZAceW9n6cGY5gh4E4yRv-FoiWng_y1tHN8vUliZCIDi1F_&_nc_ohc=CzWM_LAi3egAX9eNjmi&_nc_ht=scontent.frgn5-2.fna&oh=94e5de10481e64cb4f1000d4e05f026f&oe=5EBAF509",
              title: "ထင်အောင်ခန့်စော်ရသွားပီလား2??",
              date: "ဖေ၊ ၃၀၊ ၂၀၂၀",
              shortText:
                "ထင်အောင်ခန့် စော်ရသွားလေပီ ဆိုသောသီတင်းမှာ သီတင်းမှားသာဖြစ်ကြောင်း မအူပင်ကွန်ပျူတာတက္ကသိုလ်မှ ပြောရေးဆိုခွင့်ရှိသူ ခန့်ညီအောင်(ခ)အုပ်ကြီးမှ ပြောကြားပါတယ်။ ယခုအချိန်မှာတော့ သီတင်းမှားဖြန့်ဝေသူ ကိုကောင်းမြတ်ပိုင်ကို တောင်ဥက္ကလာမြို့မရဲစခန်းမှာ ဖမ်းဆီးထိန်းသိမ်းထားပီး တရားဥပဒေအရ အရေးယူသွားမည်ဖြစ်ကြောင်း တောင်ဥက္ကလာမြို့မရဲစခန်း စခန်းမှူး ကိုအဝတ်စုတ်မှ ကျွန်တော်တို့ စောက်ချောကြီး media ကိုဖြေကြားခဲ့ပါတယ်။"
            }
          ]
        }
      ]
    };
  },

  methods: {
    search: function(searchValue) {
      this.searchHistory.push(searchValue);
    }
  }
};
</script>

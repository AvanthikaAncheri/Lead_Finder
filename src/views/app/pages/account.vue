<template>
  <div class="main-content">
    <MainHeader></MainHeader>
    <main>
      <b-carousel
        id="carousel-1"
        :interval="4000"
        controls
        indicators
        variant="dotted"
      >
        <b-carousel-slide>
          <template #img>
            <div class="p-5" style="background-color: #00BD84;height: 200px;">
              <div class="slide">
                <div class="slide-content">
                  <div class="current-plan">Current Plan</div>
                  <div class="free-trail">{{current_plan.plan}} Plan</div>
                  <div class="slide-btn">
                      <div class="upgrade-now">Upgrade Now</div>
                  </div>
                </div>
                <img class="" style="height: 120px;width: 150px;" src="/images/slide-img1.png" alt="image slot"> 
              </div>
            </div>
          </template>
        </b-carousel-slide>
        <b-carousel-slide>
          <template #img>
            <div class="p-5" style="background-color: #00BD84;height: 200px;">
              <div class="slide-box">
                  <div class="slide-box1">
                      <div class="slide-num">
                          <div class="slide-num1">79</div>
                          <div class="left">Left</div>
                      </div>
                      <div class="lead-finder">Lead Finder</div>
                  </div>
                  <div class="slide-box1">
                      <div class="slide-num">
                          <div class="slide-num1">39</div>
                          <div class="left">Left</div> 
                      </div>
                      <div class="lead-finder">CRM</div>
                  </div>
              </div>
            </div>
          </template>
        </b-carousel-slide>
      </b-carousel>
      <div class="accounts">
      <div class="profile">
        <div class="profile-content">
          <div class="profile-name">{{profile.name}}</div>                       
          <div class="profile-email">{{profile.email}}</div>
        </div>
        <div class="profile-pic">
          <img :src="profile.profile_picture?profile.profile_picture:'/images/profile-pic.png'" alt="" style="height: 50px;width: 50px;border-radius: 50%;">
        </div>
      </div>

      <div class="account-section" v-b-modal.account-modal>
        <img src="/images/Account.png" alt="" width="24px" height="24px" style="position: relative;">
        <div class="account-details">
            <div class="account-text">Account</div>
            <div class="detail-text">Personal Details</div>
        </div>
      </div>
      <div class="account-section" @click="getPlans()" v-b-modal.plans-modal>
          <img src="/images/Subscription.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">Subscription</div>
              <div class="detail-text">Upgrade your current free plan</div>
          </div>
      </div>
      <div class="account-section">
          <img src="/images/How to use.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">How to Use?</div>
              <div class="detail-text">Guide for finding leads</div>
          </div>
      </div>
      <div class="account-section">
          <img src="/images/Download.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">Download Data</div>
              <div class="detail-text">Download detailed data reports for analysis</div>
          </div>
      </div>
      <div class="account-section">
          <img src="/images/Tag.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">Category Report</div>
              <div class="detail-text">Get category-specific reports</div>
          </div>
      </div>
      <div class="account-section" v-b-modal.support-ticket>
          <img src="/images/Support.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">Support & Tickets</div>
              <div class="detail-text">Create Tickets and inquiries</div>
          </div>
      </div>
      <div class="account-section">
          <img src="/images/Exit.png" alt="" width="24px" height="24px" style="position: relative;">
          <div class="account-details">
              <div class="account-text">Sign out</div>
          </div>
      </div>
  

      </div>
    </main>
    <div>
      <b-modal id="account-modal" class="modal-11" hide-header hide-footer>
        <div class="modal11-main">
        <div class="modal11-header">
          <div class="account-text2">Account</div>
          <div class="close-btn">
            <button class="btn-bg" @click="$bvModal.hide('account-modal')">
              <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
            </button>
          </div>
        </div>
        <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;"></div> 
        <div class="modal11-content">
          <div class="modal11-inner">
            <img :src="profile.profile_picture?profile.profile_picture:'/images/profile-pic.png'" alt="" style="height: 65px;width: 65px;border-radius: 50%;">
            <div class="modal11-profile">
              <div class="m11-name">{{profile.name}}</div>
              <div class="m11-contact">
                <div class="m11-mail">{{profile.email}}</div>
                <div class="m11-mobile">{{profile.phone}}</div>
              </div>
            </div>
            <div class="m11-editprfle" v-b-modal.profile-edit>
              <div class="m11-prfletext">Edit Profile</div>
            </div>
          </div>
          <div class="m11-plans">
            <div class="m11-plans-content">
              <div class="m11-currentplan">Current Plan</div>
              <div class="m11-premium">{{current_plan.plan}}</div>
              <div class="m11-leads">{{parseInt(plan_info.used_leads)}}/{{current_plan.leads==-99?'Unlimited':current_plan.leads}} leads used</div>
            </div>
            <div class="m11-cancel" v-b-modal.cancel-plan>
              <div class="m11-cancel-plan">Cancel Plan</div>
            </div>
          </div>
        </div>
        <button class="m11-delete-btn" v-b-modal.delete-account>
          <div class="m11-delete">Delete Account</div>
        </button>
        </div>
      </b-modal>
      
      <b-modal id="profile-edit" class="modal-12" title="" hide-header hide-footer>
        <div class="modal12-main">
          <div class="modal12-contents">
            <div class="modal12-header">
              <div class="modal12-edit-container">
                <button class="btn-arrow" @click="$bvModal.hide('profile-edit')">
                  <img src="/images/Arrow-back.png" alt="" width="24px" height="24px" style="position: relative;">
                </button>
                <div class="edit-profile-text">Edit Profile</div>
              </div>
              <div class="close-btn">
                  <button class="btn-bg" @click="$bvModal.hide('profile-edit')">
                      <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                  </button>
              </div>
            </div>
            <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;"></div> 
              <div class="modal12-profile">
                <form class="modal12-profile">
                  <div class="modal12-image">
                    <label style="position: relative;">
                      <img :src="profile.profile_picture?profile.profile_picture:'/images/profile-pic.png'" alt="" style="height: 85px;width: 85px;border-radius: 50%;">
                      <div class="modal12-image2" style="position: absolute;right: -3px;bottom: -3px;">
                        <img src="/images/add-prfle.png" alt="" width="25.2px" height="25.2px" style="position: relative;background-color: #00BD84;border-radius: 9999px;">
                      </div>
                      <input type="file" v-show="false">
                    </label>
                  </div>
                  <div class="modal12-details">
                    <div class="modal12-detail-box">
                        <div class="modal12-name">
                          <div class="modal12-enter-name">Enter Name</div>
                        </div>
                        <div class="modal12-enter-detail">
                          <input type="name" id="input-text" placeholder="Name" v-model="profile.name" style="width: 100%;border: none;">
                        </div>
                    </div>
                    <div class="modal12-detail-box">
                        <div class="modal12-name">
                          <div class="modal12-enter-name">Enter email</div>
                        </div>
                        <div class="modal12-enter-detail">
                          <input type="email" id="input-text" placeholder="Email" v-model="profile.email" style="width: 100%;border: none;">
                        </div>
                    </div>
                    <div class="modal12-detail-box">
                        <div class="modal12-phone">
                          <div class="modal12-enter-name">Enter Phone</div>
                        </div>
                        <div class="modal12-enter-detail">
                          <input type="phone" id="input-text" placeholder="Phone" v-model="profile.phone" style="width: 100%;border: none;">
                        </div>
                    </div>
                  </div>
                  <div class="btn-17">
                    <button type="submit" class="modal12-btn">
                      <div class="modal12-btn-text">Save</div>
                    </button>
                  </div>
                </form>
              </div>
          </div>
        </div>
      </b-modal>
      
      <b-modal id="plans-modal" class="modal-15" hide-header hide-footer>
        <div class="m15-main">
          <div class="modal11-header">
            <div class="account-text2">Pick Your plan</div>
            <div class="close-btn">
              <button class="btn-bg" @click="$bvModal.hide('plans-modal')">
                <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
              </button>
            </div>
          </div>
          <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;"></div> 
          <div class="checkbox15">
            <div class="m15-checkbox" v-for="(plan,key) in plans" @click="selected_plan=plan" :class="selected_plan.id==plan.id?'active-plan':''" v-if="($root.offer_count.day>=0 && plan.type=='Offer') || plan.type!='Offer'">
              <div class="m15-checkbox-content">
                <div class="m15-starter-text">{{plan.plan}}</div>
                <div class="m15-usd-text"><span class="USD">${{ plan.amount }} USD</span><span class="per-month">Per {{plan.lead_duration}}</span></div>
                <div class="m15-lead-limit">{{plan.description}}</div>
              </div>
              <div class="m15-checkmark-box">
                <input type="checkbox" class="m15-checkmark" name="selected_plan" v-model="selected_plan.id" :value="plan.id" />
                <span class="checkmark1"></span>
              </div>
            </div>
            <div class="btn-17" ></div>
            <button type="button" class="modal12-btn" v-b-modal.payment-failed v-if="selected_plan.id" @click="choosePlan(selected_plan.id)">
              <div class="modal12-btn-text" id="plan_btn_new">{{selected_plan.id==current_plan.id?'Subscribed':'Upgrade Now'}}</div>
            </button>
          </div>
        </div>
      </b-modal>
      
      <b-modal id="payment-failed" class="modal-18" title="" hide-header hide-footer>
        <div class="m18-payment">
          <img src="/images/payment.gif" alt="" width="200px" height="200px" style="position: relative;left: 88px; top: 137px;">
          <div class="payment-fail">Payment Failed </div>
          <div class="payment-failed">We can't process your payment. Check your internet connection and try again</div>
        </div>
        <div class="m18-container">
          <div class="m18-box">
          <div class="m18-box-content">
            <div class="m18-starter">Starter</div>
            <div style="text-align: center"><span class="m18-usd">$9 USD</span><span class="m18-permonth">Per month</span></div>
          </div>
        </div>
        <button type="button" class="m18-btn">
          <div class="m18-btn-text">Try Again</div>
        </button>
        <div class="m18-cancel" @click="$bvModal.hide('payment-failed')">>
          <div class="m18-cancel-text">Cancel</div>
        </div>
        </div>
        
      </b-modal>
      
      <b-modal id="cancel-plan" class="modal-13" title="" hide-header hide-footer>
        <div class="modal13-content">
          <div class="modal13-cancel-text">Are you sure you want to cancel your plan?</div>
          <div style="align-self: stretch; height: 0px; border: 1px #D9D9D9 solid;margin-top: 30px;"></div>
          <div class="modal13-cancel-plan">You can cancel your free plan</div>
        </div>
        <div class="btn-17">
          <div class="modal13-btns">
          <div class="modal13-btn-inner">
            <button class="modal13-btn-outline">
              <div class="modal13-btn-text">Confirm</div>
            </button>
            <button class="modal13-btn-outline1">
              <div class="modal13-btn-text1">Cancel</div>
            </button>
          </div>
        </div>
        </div>
      </b-modal>
      
      <b-modal id="support-ticket" class="modal-16" title="" hide-header hide-footer>
        <div class="m16-support">
          <div class="m16-support-contents">
              <div class="modal11-header">
                  <div class="account-text2">Supports & Tickets</div>
                  <div class="close-btn">
                      <button class="btn-bg" @click="$bvModal.hide('support-ticket')">
                        <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                    </button>
                  </div>
              </div>
              <div class="create-ticket" v-b-modal.create-ticket>
                <img src="/images/Add.png" alt="" width="24px" height="24px" style="position: relative;">
                <div class="ticket-content">
                  <div class="create-ticket-text">Create Ticket</div>
                  <div class="create-text1">Create tickets to resolve any issues</div>
                </div>
              </div>
              <div class="m16-contents">
              <div class="your-ticket">Your Ticket</div>
              <div class="m16-lead-finding">
                <div class="m16-lead-box">
                  <div class="billing">Billing</div>
                  <div class="m16-lead-text">I couldn't upload my profile pictur...</div>
                </div>
                  <div class="m16-send-box">
                  <img src="/images/send.png" alt="" width="18px" height="18px" style="position: relative;">
                  <div class="m16-send-text">Send</div>
                  </div>
              </div>
              <div class="m16-lead-finding">
                <div class="m16-lead-box">
                  <div class="billing">Lead Finding</div>
                  <div class="m16-lead-text">I couldn't upload my profile pictur...</div>
                </div>
                  <div class="m16-send-box">
                  <img src="/images/send.png" alt="" width="18px" height="18px" style="position: relative;">
                  <div class="m16-send-text">Send</div>
                  </div>
              </div>
              <div class="m16-lead-finding">
                <div class="m16-lead-box">
                  <div class="billing">Lead Finding</div>
                  <div class="m16-lead-text">I couldn't upload my profile pictur...</div>
                </div>
              </div>
              </div>
              <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;margin-top: 30px;"></div>
              <div class="btn-17">
              <button class="m16-button">
              <img src="/images/Email.png" alt="" width="20px" height="24px" style="position: relative;">
              <div class="support-email">Support email</div>
              </button>
              </div>
          </div>
        </div>
      </b-modal>
      
      <b-modal id="create-ticket" class="modal-17" title="" hide-header hide-footer>
        <div class="modal11-header">
          <div class="account-text2">Create Ticket</div>
            <div class="close-btn">
              <button class="btn-bg" @click="$bvModal.hide('create-ticket')">
                <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
              </button>
            </div>
        </div>
        <div class="m17-content">
          <div class="m17-category">
          <div class="category-outline">
            <div class="category-text">Category</div>
          </div>
          <div class="billing-content">
            <div class="billing-text">Billing</div>
                <img src="/images/arrow-down-s.png" alt="" width="24px" height="24px" style="position: relative;">
            </div>
          </div>
          <div class="m17-comment">
          <div class="comment-outline">
            <div class="comment-text">Enter comment</div>
          </div>
          <div class="comment-text1">I couldn't upload my profile picture</div>
          </div>
          <button type="button" class="modal12-btn" style="margin-top: 20px;">
              <div class="modal12-btn-text">Create ticket</div>
          </button>
        </div>
      </b-modal>
      
      <b-modal id="delete-account" class="modal-14" title="" hide-header hide-footer>
        <div class="modal13-content">
            <div class="modal13-cancel-text">Are you sure you want to delete the account?</div>
            <div style="align-self: stretch; height: 0px; border: 1px #D9D9D9 solid;margin-top: 30px;"></div>
            <div class="modal13-cancel-plan">All your data will be completely deleted and you won't be able to recover it.</div>
        </div>
        <div class="btn-17">
          <div class="modal14-btns">
            <div class="modal13-btn-inner">
              <button class="modal13-btn-outline">
                <div class="modal13-btn-text">Cancel</div>
              </button>
              <button class="modal14-btn-outline1">
                <div class="modal13-btn-text1">Delete</div>
              </button>
            </div>
          </div>
        </div>
      </b-modal>
    </div>
  </div>
</template>

<script>
import MainHeader from '/src/views/app/pages/account-header'
// import MainFooter from '/src/views/app/pages/footer'
export default{
  metaInfo: {
    title: "Home"
  },
  components:{
    MainHeader
    
  },
  data(){
    return {
      profile:{},
      current_plan:{},
      plan_info:{used_crm: 0,used_emails: 0,used_leads: 159,used_newsletters: 0},
      plans:[],
      selected_plan:{id:null},
      crnt_tab: 'tab1',
      crnt_tab_profile: 'profile',
      free_plan:false,
      logo_tab: 'logo1',
      tickets:[],
      current_ticket:{id:null, name:'', messages:[]},
    };
  },
  mounted(){
    if(this.$route.query.auth_token){
      this.$root.auth_token = this.$route.query.auth_token
      localStorage.setItem("auth_token",this.$root.auth_token)
    }
    if(this.$root.auth_token){
      this.getProfile()
    }
  },
  methods : {
    getProfile() {
      var headers = new Headers();
      headers.append("Authorization", "Bearer "+this.$root.auth_token);
      fetch(this.api_url+'/employee/user_data/', {
          method : 'get',
          headers: headers,
      })
      .then((response) => {
          return response.json()
      })
      .then((jsonData) => {
        if(jsonData.success){
          this.current_plan = jsonData.current_plan.plan_details
          this.plan_info = jsonData.current_plan
          this.profile = jsonData.user
        }
      })
    },
    getPlans(){
      var headers = new Headers();
      headers.append("Authorization", "Bearer "+this.$root.auth_token);
      fetch(this.api_url+'/employee/plans/?currently_active=active', {
          method : 'get',
          headers: headers,
      })
      .then((response) => {
          return response.json()
      })
      .then((jsonData) => {
        this.plans = jsonData
        // if(jsonData.length>0 && this.$root.offer_count.day>=0){
        //   this.selected_plan = jsonData[0]
        // }
      })
    },
    choosePlan(plan_id){
      var method = 'POST'
      var params = ''
      if(this.profile.payment_method){
        method = 'PUT'
        params = this.profile.payment_method+'/'
      }
      if(this.$root.lock_btn){
        return false
      }
      this.$root.lock_btn = true
      document.getElementById('plan_btn_new').innerHTML = 'Please Wait..'
      var headers = new Headers();
      var formdata = new FormData()
      formdata.append('plan_id',plan_id)
      headers.append("Authorization", "Bearer "+this.$root.auth_token);
      fetch(this.api_url+'/employee/stripe_payments/'+params, {
          method : method,
          headers: headers,
          body: formdata,
      })
      .then((response) => {
          return response.json()
      })
      .then((data) => {
        if(data.success)
        {
          if(data.payment_url){
            // $('body').html(data.form)
            location.href=data.payment_url
          }else{
            this.$root.lock_btn = false
            document.getElementById('plan_btn_new').innerHTML = 'Subscribed'
          }
        }else{
          this.$root.lock_btn = false
          document.getElementById('plan_btn_new').innerHTML = 'Subscribe Now'
        }
      })
    },
  }
};
</script>
<style scoped>

@import './style/style.css';
  
</style>
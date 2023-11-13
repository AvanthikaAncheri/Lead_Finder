<template>
    <div class="main-content">
        <header>
            <div class="home-header">
                <div class="home-header-container">
                    <h1 id="home">Dashboard</h1>
                    <router-link to="/account">
                        <img src="/images/profile-home.png" width="20px" height="20px" id="home-icon">
                    </router-link>
                </div>
           </div>
       </header>
       <div class="summary">
          <div class="summary-text">Summary</div>
          <router-link to="/view-more">
            <div class="view-more">View more</div>
          </router-link>
       </div>
       <div class="home-box">
        <div class="home-box-content">
            <div class="home-box-inner">
                <div class="home-download-box">
                    <div class="home-num">0</div>
                    <div class="home-download-leads">Download Leads</div>
                </div>
                <div class="home-download-box1">
                    <div class="home-num">0</div>
                    <div class="home-download-leads">Email Marketing</div>
                </div>
            </div>
            <div class="home-box-inner1">
                <div class="home-download-box">
                    <div class="home-num">0</div>
                    <div class="home-download-leads">Search Categories</div>
                </div>
                <div class="home-download-box1">
                    <div class="home-num">0</div>
                    <div class="home-download-leads">Saved Leads</div>
                </div>
            </div>
        </div>
       </div>
       <div class="home-section1">
        <div style="align-self: stretch; height: 0px; border: 1px #D9D9D9 solid"></div>
        <div class="home-content1">
            <div class="home-content1-inner">
                <div class="home-container1">
                    <div class="home-head-text1">Find leads for your business</div>
                    <div class="home-para-text1">Platform, list, content, segment, test, track, stay compliant for customer growth.</div>
                    <button type="button" class="home-btn1" @click="redirectTo('lead_finding')">
                        <div class="home-btn-text">Find Leads now</div>
                   </button>
                </div>
            </div>
            <img src="/images/image1.png" alt="" width="110px" height="133.9px">
        </div>
        <div style="align-self: stretch; height: 0px; border: 1px #D9D9D9 solid"></div>
        <div class="home-content1">
            <div class="home-content1-inner">
                <div class="home-container1">
                    <div class="home-head-text1">Setup CRM</div>
                    <div class="home-para-text1">Platform, list, content, segment, test, track, stay compliant for customer growth.</div>
                    <button type="button" class="home-btn1" @click="redirectTo('crm')">
                        <div class="home-btn-text">Go to CRM</div>
                   </button>
                </div>
            </div>
            <img src="/images/image2.png" alt="" width="120px" height="112.2px">
        </div>
        <div style="align-self: stretch; height: 0px; border: 1px #D9D9D9 solid"></div>
        <div class="home-content1">
            <div class="home-content1-inner">
                <div class="home-container1">
                    <div class="home-head-text1">Setup Email Marketing</div>
                    <div class="home-para-text1">Platform, list, content, segment, test, track, stay compliant for customer growth.</div>
                    <button type="button" class="home-btn1">
                        <div class="home-btn-text">Go to Setup</div>
                   </button>
                </div>
            </div>
            <img src="/images/image3.png" alt="" width="107px" height="82px">
        </div>
       </div>
       <MainFooter></MainFooter>
    </div> 
</template>  
<script>
import MainFooter from '/src/views/app/pages/footer'
export default{
    metaInfo: {
        title: "Lead Finder"
    },
    components:{
        MainFooter
    },
    data() {
        return {
        };
    },
    mounted(){
      if(this.$route.query.auth_token){
        this.$root.auth_token = this.$route.query.auth_token
        localStorage.setItem("auth_token",this.$root.auth_token)
      }
    }
}; 
</script> 
<style scoped>
@import './style/style.css';
</style>
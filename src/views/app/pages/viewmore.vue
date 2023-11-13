<template>
    <div class="main-content">
        <header>
            <div class="home-header">
                <div class="home-header-container">
                     <h1 id="home">Dashboard</h1>
                     <img src="/images/profile-home.png" width="20px" height="20px" id="home-icon">
                </div>
           </div>
       </header>
       <div class="summary">
            <div class="summary-text">Summary</div>
            <router-link to="/">
                <div class="view-more">Home</div>
            </router-link>
       </div>
       <div class="home-box">
        <div class="home-box-content">
            <div class="home-box-inner">
                <div class="home-download-box">
                    <div class="home-num">56</div>
                    <div class="home-download-leads">Download Leads</div>
                </div>
                <div class="home-download-box1">
                    <div class="home-num">126</div>
                    <div class="home-download-leads">Email Marketing</div>
                </div>
            </div>
            <div class="home-box-inner1">
                <div class="home-download-box">
                    <div class="home-num">84</div>
                    <div class="home-download-leads">Search Categories</div>
                </div>
                <div class="home-download-box1">
                    <div class="home-num">06</div>
                    <div class="home-download-leads">Saved Leads</div>
                </div>
            </div>
        </div>
       </div>
       <div class="view-section">
        <div class="email-marketing">
           <div class="email-text">Email Marketing</div>
           <div class="email-content">
            <div class="email-container">
                <div style="width: 12px; height: 12px; background: #02D55A; border-radius: 9999px"></div>
                <div class="email-text1">Email</div>
            </div>
            <div class="email-container">
                <div style="width: 12px; height: 12px; background: #9747FF; border-radius: 9999px"></div>
                <div class="email-text1">SMS</div>
            </div>
           </div>
        </div>
       </div>
       <div class="graph">
        <img src="/images/graph1.png" alt="" width="100%" height="auto" style="position: relative;">
       </div>
       <div class="marketing-overview">
         <div class="marketing-text">Marketing Overview</div>
         <div class="year-section">
            <img src="/images/arrow-home.png" alt="" width="24px" height="24px" style="position: relative;">
            <div class="year-text">2022</div>
            <img src="/images/arrow2-home.png" alt="" width="24px" height="24px" style="position: relative;">
         </div>
       </div>
       
       
       <div class="section2">
            <div class="analysis">
                 <div class="analysis-section">
                     <img src="/images/eclipse1.png" alt="" width="80px" height="80px" style="position: relative;">
                     <div class="percentage">46%</div>
                 </div>
                 <div class="analysis-content">
                    <div class="analysis-text1">56</div>
                    <div class="analysis-text2">Download Leads</div>
                </div>
           </div>
           <div class="analysis">
                 <div class="analysis-section">
                     <img src="/images/eclipse2.png" alt="" width="80px" height="80px" style="position: relative;">
                     <div class="percentage">56%</div>
                 </div>
                 <div class="analysis-content">
                    <div class="analysis-text1">56</div>
                    <div class="analysis-text2">Emailed Marketing</div>
                </div>
           </div>
           <div class="analysis">
                 <div class="analysis-section">
                     <img src="/images/eclipse3.png" alt="" width="80px" height="80px" style="position: relative;">
                     <div class="percentage">100%</div>
                 </div>
                 <div class="analysis-content">
                    <div class="analysis-text1">56</div>
                    <div class="analysis-text2">Saved Leads</div>
                </div>
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
    }
}; 
</script>  
<style scoped>
@import './style/style.css';
</style>
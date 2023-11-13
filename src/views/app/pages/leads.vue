<template>
  <div class="main-content">
    <MainHeader></MainHeader>
    <main>
      <div class="ld-main" v-if="is_not_start">
         <div class="main-load">
           <div class="ld-section1">
             <div class="ld-content1"></div>
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>
           <div class="ld-section2">
               <div class="ld-content2">
                  <div class="ld-content21"></div>
                  <div class="ld-content22"></div>
               </div>
              <div class="ld-content23">
                 <div class="ld-content231"></div>
                 <div class="ld-content232"></div>
                 <div class="ld-content24"></div>
              </div>
              
           </div>

         </div>
      </div>
      <div class="main" v-else> 
        <div class="content-date">
        <div class="contentdate-items">
          <div class="text-date1">Wednesday, Oct 04</div>
          <div class="btn-date">
            <div class="text-date2">Today</div>
          </div>
        </div>
       </div>
       <div class="car-wash" v-for="lead in leads">
         <b-card class="content-car">
          <div class="card-body" v-b-modal.modal-1>
            <div class="contentcar-items">
              <b-card-text class="car-wash-text">{{lead.category_name}}</b-card-text>
              <b-card-text class="car-wash-name">{{lead.name}}</b-card-text>
            </div>
            <div class="car-wash-time">
              <b-button class="car-period">
                <div class="car-new">{{lead.lead_status}}</div>
              </b-button>
              <div class="car-time">{{timeAgo(lead.created_on)}}</div>
            </div>     
          </div>
         </b-card>
       </div>
      </div>
    </main>
    
    <div class="main-footer">
       <footer>
         <div class="download">
           <div class="download-box" v-b-modal.modal-5>
              <div class="download-img">
                  <img src="/images/download-line.png" alt="" width="20px" height="20px" style="position: relative;">
              </div>
              <div class="download-text">Download Leads</div>
            </div>
        </div>
    </footer>
    
    <b-modal id="modal-1" class="modal-1" title="" hide-header hide-footer>
      <div style="width: 72px; height: 5px; background: #D9D9D9; border-radius: 8px;margin-top: 8px;margin-left: 50%;"></div>
      <header id="modal-header" class="modal-header">
        <div class="lead">
          <h5 id="modal-title">Lead Details</h5>
        </div> 
        <div class="modal0-close">
            <button class="modal0-close-btn" aria-label="Close" @click="$bvModal.hide('modal-1')">
                <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
            </button>
        </div>
        </header>
        <div class="modal-content">
          <div class="modal-details">
            <div class="modal-new">
                  <div class="new-text">New</div>
                  <div class="arrow-down"><img src="/images/arrow-down-s.png" alt="" width="24px" height="24px" style="position: relative;"></div>
              </div>
            </div>
            <div class="modal-car">
                  <div class="modal-car-text">Octopus Car Spa</div>
                  <div class="modal-car-content">
                    <img src="/images/Map.png" alt="" width="20px" height="20px" style="position: relative;">
                    <div class="modal-car-details">8B, Summer sandal canal Road Thrikkakkara, Kochi</div>
                  </div>
          </div>
          <div  id="modal-car-contact">
                  <div  id="modal-car-wash">
                      <img src="/images/Briefcase.png" alt="" width="20px" height="20px" style="position: relative;">
                      <div class="modal-wash-text">Car Wash</div>
                  </div>
                  <div  id="modal-car-mobile">
                    <img src="/images/phone-line.png" alt="" width="20px" height="20px" style="position: relative;">
                    <div class="modal-mobile-text">+91974689545</div>
                  </div>
                  <div  id="modal-email">
                    <div class="modal-car-email">
                                <img src="/images/Email.png" alt="" width="20px" height="20px" style="position: relative;">
                              <div class="modal-email-text">Not available</div>
                      </div>
                      <div class="modal-add-email">Add Email</div>
                  </div>
                  <div  id="modal-car-web">
                    <img src="/images/Web.png" alt="" width="20px" height="20px" style="position: relative;">
                      <div class="modal-web-text">www.octopuscarspaservice.com</div>
                  </div>
          </div>
          <div class="modal-buttons">
            <div class="modal-button1" v-b-modal.modal-2>
              <img src="/images/addicon.png" alt="" width="20px" height="20px" style="position: relative;">
                        <div class="add-text">Add Note</div>
              <b-modal id="modal-2" title="" hide-header hide-footer>
                <div class="modal-2">
                  <header class="modal2-content">
                    <div style="width: 72px; height: 5px; background: #D9D9D9; border-radius: 8px;margin-top: 8px;text-align: center;"></div>
                  <div class="modal2-header">
                    <button type="button" class="modal2-header-content" aria-label="Close" @click="$bvModal.hide('modal-2')">
                          <img src="/images/Arrow-back.png" alt="" width="24px" height="24px" style="position: relative;">
                    </button>
                      <div class="modal2-header-text">Note</div>
                  </div>
                  <div class="modal2-close">
                    <button class="modal2-close-btn" aria-label="Close" @click="$bvModal.hide('modal-2')">
                      <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                    </button>
                  </div>
                </header>
                <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;"></div> 
                <div class="modal2-box">
                  <div class="modal2-description">
                  <div class="description-text-box">
                    <div class="description-text">Enter Description</div>
                  </div>
                  <div class="add-note">Add your Note</div>
                </div>
                </div>
                <div class="button-save-note">
                  <button class="log-save-activity">
                            <div class="log-save-text">Save Note</div>
                      </button>
                </div>
                
                </div>
              </b-modal>
            </div>
            <div class="modal-button2" v-b-modal.modal-3>
              <img src="/images/log.png" alt="" width="20px" height="20px" style="position: relative;">
                    <div class="log-activity">Log Activity</div>
              <b-modal id="modal-3" title="" hide-header hide-footer>
                <div class="modal3-main">
                  <div class="modal3-container">
                    <div style="width: 72px; height: 5px; background: #D9D9D9; border-radius: 8px;margin-top: 8px;text-align: center;"></div>
                    <header class="modal3-items">
                      <div class="modal3-header">
                        <button type="button" class="modal3-arrow" aria-label="Close" @click="$bvModal.hide('modal-3')">
                          <img src="/images/Arrow-back.png" alt="" width="24px" height="24px" style="position: relative;">
                        </button>
                        <div class="modal3-headertext">
                          Log Activity
                        </div>
                        <div class="modal3-close">
                            <button type="button" class="modal3-butn" aria-label="Close" @click="$bvModal.hide('modal-3')">
                              <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                            </button>
                        </div>
                      </div>
                    </header>
                    <div style="width: 100%; height: 0; border: 1px #D9D9D9 solid;"></div> 
                    <div class="modal-log-content">
                      <div class="log-activity-text">Add your log Activity here</div>
                    </div>
                        <div class="log-buttons">
                          <button type="button" class="log-butn1">
                            <div class="logbutn-text">Call</div>
                          </button>
                          <button type="button" class="log-butn1">
                            <div class="logbutn-text">Mail</div>
                          </button>
                        </div>
                        <div class="modal-log-box">
                          <div class="modal-log-description">
                          <div class="log-description-box">
                            <div class="log-description-text">Enter Activity</div>
                          </div>
                          <div class="log-add-description">Add your Activity</div>
                        </div>
                        </div>
                      </div>
                      <div class="logdate-time-butn">
                      <button type="button" class="logdate-btn1">
                        <div class="log-date-outline">
                          <div class="log-date-text">Date</div>
                        </div>
                        <input type="date"  id="log-date">
                      </button>
                      <button type="button" class="logdate-btn2">
                        <div class="log-date-outline">
                        <div class="log-date-text">Time</div>
                        </div>
                        <input type="time"  id="log-time">
                      </button>
                      </div>
                      <div class="save-activity">
                      <button class="log-save-activity">
                            <div class="log-save-text">Save Activity</div>
                      </button>
                      </div>
                    
                </div>
              </b-modal>
                    
              </div>
          </div>

        </div>
    </b-modal>
    
    <b-modal id="modal-5" class="modal-5" title="" hide-header hide-footer>
      <div class="download-leads">
        <div class="dwnld-leads-content">
          <div style="width: 72px; height: 5px; background: #D9D9D9; border-radius: 8px;margin-top: 8px;text-align: center;"></div> 
          <header class="download-header">
            <div class="dwnld-header-items">
              <div class="dwnld-header-text">Download Leads</div>
              <div class="modal0-close">
                  <button class="modal0-close-btn" aria-label="Close" v-b-modal.modal-5>
                      <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                  </button>
              </div>
            </div>
          </header>
          <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;margin-top: -30px;"></div> 
          <div class="dwnld-categories">
            <div class="dwnld-category-box">
                <div class="dwnld-category-text">Category</div>
                <div class="dwnld-wash-box">
                  <div class="dwnld-wash-text">Car Wash</div>
                  <img src="/images/arrow-down-s.png" alt="" width="24px" height="24px" style="position: relative;margin-left: 5px;">
                </div>
            </div>
            <div class="dwnld-category-box">
              <div class="dwnld-category-text">Status</div>
              <div class="dwnld-wash-box">
                <div class="dwnld-wash-text">All</div>
                <img src="/images/arrow-down-s.png" alt="" width="24px" height="24px" style="position: relative; margin-left: 5px;">
              </div>
            </div>
          </div>
          <div class="dwnld-advanced-settings">
            <b-dropdown>
              <template #button-content>
                  <div class="advncd-setting-text">
                    <div class="advanced-text">Advanced Settings</div>
                    <img src="/images/arrow-down-crm.png" alt="" width="24px" height="24px" style="position: relative;">
                  </div>
              </template>
              <div class="logdate-time-butn">
                      <b-dropdown-item class="logdate-btn1">
                        <div class="log-date-outline">
                          <div class="log-date-text">Start Date</div>
                        </div>
                        <input type="date"  id="log-date">
                      </b-dropdown-item>
                      <b-dropdown-item class="logdate-btn2">
                        <div class="log-date-outline">
                        <div class="log-date-text">End Date</div>
                        </div>
                        <input type="date"  id="log-date">
                      </b-dropdown-item>
                    </div>
              
            </b-dropdown>
              </div>
          <div class="download-section">
            <div class="section-tags">Tags</div>
            <div class="section-survey">
              <div class="dwnld-survey-box">
                <div class="dwnld-survey-text">Survey 2023</div>
              </div>
              <div class="dwnld-survey-box">
                <div class="dwnld-survey-text">Local Database-1</div>
              </div>
              <div class="dwnld-survey-box">
                <div class="dwnld-survey-text">Local Database-2</div>
              </div>
            </div>
          </div>
          <div class="download2" v-b-modal.modal-51>
            <div class="download-box">
              <div class="download-img">
                  <img src="/images/download-line.png" alt="" width="20px" height="20px" style="position: relative;">
              </div>
              <div class="download-text">Download (72) Leads</div>
            </div>
          </div>
        </div>
      </div>
    </b-modal>
            
    <b-modal id="modal-51" class="modal-51" title="" hide-header hide-footer>
      <div class="btn-img" style="justify-content: center;align-items: center;text-align: center;">
        <img src="/images/download-btn.gif" alt="" width="100px" height="100px" style="align-items: center;justify-content: center;margin-top: 80px;">
      </div>
      <div class="m51-download">Download data successful, Please check your email</div>
      <div class="m51-download-box1">
        <div class="download-box1">
          <div class="download-text1">Back to CRM</div>
        </div>
      </div>
    </b-modal>
    </div>
  </div>
</template>
<script>
  import MainHeader from '/src/views/app/pages/header'
  export default{
    metaInfo: {
      title: "Lead Finder"
    },
    components:{
      MainHeader
    },
    data() {
      return {
        is_not_start : true,
        background_start:true,
        lastScrollPosition: 0,
        lead_categories:[],
        leads:[],
        category_ids:[],
        current_status:'Status',
        is_loading:true,
      };
    },
    mounted(){
      // var self = this
      // document.getElementsByClassName("lead-main")[0].addEventListener("scroll", () => {
      //     self.handleScroll()
      // });
      this.$root.crm_active='leads'
      if(this.$route.query.auth_token){
        this.$root.auth_token = this.$route.query.auth_token
        localStorage.setItem("auth_token",this.$root.auth_token)
      }
      if(this.$root.auth_token){
        this.getUser()
      }
      this.getLeads()
    },
    methods:{
      getLeads() {
        this.is_loading = true
        var headers = new Headers();
        headers.append("Authorization", "Bearer "+this.$root.auth_token);
        var params = '?user_wise=yes'
        if(this.$route.query.lates){
          params+='&latest=yes'
        }
        fetch(this.api_url+'/employee/leads/'+params, {
            method : 'get',
            headers: headers,
        })
        .then((response) => {
            return response.json()
        })
        .then((jsonData) => {
          this.is_loading = false
          this.is_not_start = false
          this.leads = jsonData
        })
      },
      categoryIds(data){
        this.category_ids = data
      },
      currentStatus(data){
        this.current_status = data
      },
    }
  }; 

</script>
<style scoped>

@import './style/style.css';
  
</style>
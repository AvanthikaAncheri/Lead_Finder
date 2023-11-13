<template>
  <div class="main-content">
     <header>
      <div class="header">
        <div class="crm-header">
          <img src="/images/arrow-left-s-line.png" width="32px" height="32px" id="crm-icon" @click="goBack()">
          <h1 id="crm">CRM</h1>
        </div>
       <div class="content">
          <div class="search-bar">
          <img src="/images/search-line.png" alt="" width="20px" height="20px" style="position: relative;">
              <div class="search">
                <input type="search" placeholder="Search leads" id="search-text">
              </div>
          </div>
          <button class="filter" v-b-modal.filter-modal>
            <img src="/images/Filter.png" alt="" width="40px" height="40px" style="position: relative;">
          </button>
        </div>
      </div> 
    </header>
    <div>
      <b-modal id="filter-modal" class="modal-1" hide-header hide-footer>
        <div class="modal-0">
          <div class="modal0-content">
            <div style="width: 72px; height: 5px; background: #D9D9D9; border-radius: 8px;margin-top: 8px;text-align: center;"></div>  
            <div class="modal0-header">
              <div class="modal0-header-text">Filter</div>
              <div class="modal0-close">
                  <button class="modal0-close-btn" @click="$bvModal.hide('filter-modal')" aria-label="Close">
                    <img src="/images/Close.png" alt="" width="24px" height="24px" style="position: relative;">
                  </button>
                </div>
              </div>
            </div>
            <div style="width: 100%; height: 100%; border: 1px #D9D9D9 solid;"></div> 
            <div class="modal0-maincontent">
              <div class="modal0-border1">
                <div class="modal0-category" id="cat01-modal0">
                  <div class="modal0-box">
                    <div class="category-name">Category</div>
                  </div>
                </div>
                <div class="modal0-category" id="cat02-modal0">
                  <div class="modal0-box">
                    <div class="category-name">Status</div>
                  </div>
                </div>
                <div class="modal0-category" id="cat03-modal0">
                  <div class="modal0-box">
                    <div class="category-name">Tags</div>
                  </div>
                </div>
              </div>
              <div class="modal0-checkbox">
                <div class="modal0-checkbox-box">
                  <div class="checkbox-text">All</div>
                  <div class="m0-checkmark-box">
                      <input type="checkbox" class="m0-checkmark" checked="checked">
                            <span class="checkmark"></span>
                    </div>
                </div>
                <div class="modal0-checkbox-box">
                  <div class="checkbox-text">Car wash</div>
                  <div class="m0-checkmark-box">
                      <input type="checkbox" class="m0-checkmark">
                            <span class="checkmark"></span>
                    </div>
                </div>
                <div class="modal0-checkbox-box">
                  <div class="checkbox-text">Hotels</div>
                  <div class="m0-checkmark-box">
                      <input type="checkbox" class="m0-checkmark">
                            <span class="checkmark"></span>
                    </div>
                </div>
                <div class="modal0-checkbox-box">
                  <div class="checkbox-text">Realestate</div>
                  <div class="m0-checkmark-box">
                      <input type="checkbox" class="m0-checkmark">
                            <span class="checkmark"></span>
                    </div>
                </div>
              </div>
              <div class="filter-btn" style="margin-top: 20px;width: 100%;">
                <button class="log-save-activity">
                  <div class="log-save-text">Update Filter</div>
                </button>
              </div>
          </div>
        </div>
      </b-modal>
    </div>
  </div>
</template>
<script>
</script>
<style scoped>

  @import './style/style.css';
  
</style>
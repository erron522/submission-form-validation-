<template>
  <!--Dr information-->
  <div class="drInfo">
    <div class="colorOverlay">
      <div class="mainLeftCol">
        <div class="drContact">
          <div class="headshot">
            <img class="headshotImg" src="../assets/images/drHeadShot.jpg" alt="Dr Jane Doe" />
          </div>
          <div class="drNames">
            <p class="drName">Dr. Jane Doe, MD</p>
            <p class="drTitle">Neurosurgeon</p>
            <p class="drAddress">1111 New Street Pkwy, Ste 145, Los Angeles, CA</p>
          </div>
        </div>
        <div class="ratingsSection">
          <div class="ratinginfo">
            <p class="ratingNumber">4.88</p>
            <p class="ratingStars">
              <span class="fa fa-star checked"></span>
              <span class="fa fa-star checked"></span>
              <span class="fa fa-star checked"></span>
              <span class="fa fa-star checked"></span>
              <span class="fa fa-star checked"></span>
            </p>
          </div>
          <div class="ratingDetails">
            <p class="ratingDesc">
              “Very professional and transparent staff. Overall, great experience. Would definitely
              recommend this provider.”
            </p>
            <p class="ratingDate-moreReviews">
              <span class="ratingDate">Yuliya S.February 3, 2025</span>
              <span class="ratingReviews"> <a href="#">See all 591 reviews</a> </span>
            </p>
          </div>
        </div>
        <div class="drHistory">
          Dr. Doe is a Board-certified family physician in Plano with over 20 years of experience
          taking care of patients in both inpatient and outpatient settings. In the past 7 years,
          she has taken care of patients after bariatric surgery as well as worked in the emergency
          room. She attained her medical degree at Shahid Beheshti University of medical sciences,
          her MPH and mother and child health residency at Tehran University, and completed her
          training as a Family Physician at Wichita Falls Family medicine program, an affiliate of
          UT Southwestern Medical Center Dr. Doe takes a whole person approach while caring for her
          patients, taking time to listen attentively and perform a detailed physical exam.
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.mainLeftCol {
  /* margin: 15px 0 0 0; */
  padding: 35px 20px 20px;
}

.drInfo {
  background: url(../assets/images/doctorSmallBg.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.drNames {
  margin: 0 0 0 5px;
  padding: 10px 0 0 0;
}

.colorOverlay {
  background-color: rgba(32, 128, 198, 0.8);
  height: 100%;
}

img.headshotImg {
  width: 100px;
  border-radius: 50px;
  border: 1px solid #fff;
}

.headshot {
  margin: 0 auto;
}

.drContact {
  display: grid;
  grid-template-columns: 30% 1fr;
}

p.drName {
  font-size: 24px;
  color: #fff;
  margin: 0 0 2px;
}
p.drTitle {
  font-size: 20px;
  color: #fff;
  margin: 0;
  font-weight: 300;
}

p.drAddress {
  font-size: 12px;
  color: #f5f4fb;
  margin: 13px 0 0 0;
}

p.ratingNumber {
  color: #000;
  font-size: 44px;
  margin: 0 0 5px;
}

.checked {
  color: orange;
}

.ratingsSection {
  background: #fafafa;
  padding: 20px 10px;
  display: grid;
  grid-template-columns: 30% 1fr;
  margin: 40px 0;
}

.ratinginfo {
  justify-self: center;
  border-right: 1px solid #666;
  padding: 0 10px 0 0;
}

p.ratingStars {
  margin: 5px 0;
}

p.ratingDesc {
  margin: 0;
  color: #666;
  font-size: 11pt;
}

p.ratingDate-moreReviews span {
  font-size: 10pt;
  color: #666;
  margin: 10px 7px;
}

span.ratingReviews a {
  color: #2080c6;
}

p.ratingDate-moreReviews {
  margin: 10px 0 0;
}

.drHistory {
  color: #fff;
  line-height: 1.6;
  margin: 75px 20px;
}
</style>

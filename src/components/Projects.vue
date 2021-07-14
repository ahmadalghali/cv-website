<template>
  <div id="projects" class="container projects">
    <h1>Projects</h1>
    <hr />
    <br />

    <div
      class="container project"
      v-for="project in projects"
      :key="project.id"
    >
      <h2 class="display-6">{{ project.title }}</h2>
      <br />
      <p class="project-description">
        {{ project.description }}
      </p>

      <br />
      <br /><br />

      <div class="project-images" v-if="project.images.length">
        <div
          :id="project.title"
          class="carousel carousel-dark slide carousel-fade"
          data-bs-ride="carousel"
        >
          <div class="carousel-inner">
            <div
              v-for="(image, index) in project.images"
              :key="image"
              :class="`carousel-item ${index == 0 ? 'active' : ''}`"
              data-bs-interval="3000"
            >
              <img :src="image" class="d-block w-100" />
            </div>
          </div>

          <button
            class="carousel-control-prev"
            type="button"
            :data-bs-target="`#${project.title}`"
            data-bs-slide="prev"
          >
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
          </button>
          <button
            class="carousel-control-next"
            type="button"
            :data-bs-target="`#${project.title}`"
            data-bs-slide="next"
          >
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
          </button>
        </div>
      </div>
      <br /><br /><br />

      <p class="h2 fs-3">Technologies:</p>
      <ul>
        <li v-for="technology in project.technologies" :key="technology">
          <p class="display-6 fs-4">{{ technology }}</p>
        </li>
      </ul>
      <br />

      <div class="ratio ratio-16x9" v-if="project.links[0].isVideo">
        <iframe
          :src="project.links[0].url"
          :title="project.links[0].title"
          allowfullscreen
          width="400"
          height="200"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          autopla
        ></iframe>

        <!-- <iframe
          width="1424"
          height="652"
          src="https://www.youtube.com/embed/-N_RZJUAQY4"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe> -->
      </div>
      <br />
      <br />
      <h3>Links:</h3>
      <div v-for="link in project.links" :key="link">
        <a :href="link.url" target="_blank" class="fs-4">{{
          link.title ? link.title : link.url
        }}</a>
        <br />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Projects",

  data() {
    return {
      projects: [
        {
          id: "1",
          title: "Timeshare",
          description:
            "I researched about timebanks considering its possible applications for online tutoring to build a non-profit service-exchange system that can give anyone access to good education. I developed a mobile app, Timeshare, which allows users to teach what they love in return for TimeCredits that can be spent to learn a new skill.",
          images: [
            "https://lh3.googleusercontent.com/bOM3GIGsbER2yRAouuZvLYdEOYv8YasWriUH_7ZJcVCo3ZNQ9YyEKPu3O8JeUBdimSXO-vcyDPGQVVuXrycWKowDRcwKNv77vS_WI0c43Zl84H-E2pIgtiAJevkNvAxCznp8yaXGFQl5zyNySAZT4gP6ybVAcmLZwywEDj8hyVfyeiyVdWqXYV1crDcmX3CdsO0eiuNOGEPVE3wNd_bZ1jUsVhsOoFh_b0HJcj8wFagGaf2sDtrdMJPbmXWBTj8s1r7OqmfCccR9dGV9C0wXaYttAWESk_DeiedZQSFibEdBOBAk5f0eKxbfUn4pePXYT6Nn3PPkThgPgQkeaQGpIvMoGpuAqjYX1VmE94DdPkUA-KSpirKq3sEp53q4Byyk5OW9_c0aGN9ellGFCyGrNyfiSkYnXI6g-KXDaaZ6cuN1us455h83zlf2T1bTpnQnLRBW-PVVyZTsJ614rG-_7A9yNmtqLl83pYU6oMefhWC8rfW4qE9gZ3ZPR-sYsFpkCSWa91OZPzbEdlTc7BFcyXZNuiLL3qkSIp3brSvL5BgjvIBxvfzrfSJ_esjUjyLYio-6IN4L5OBqJkeT0EFoNLPC2ZIgBlSYFk6Wc_iWR18VKLT0_wezCdJtuQGqRSQusH0-K8fJADh2h5l16Atsk0V10Vl7h2gzGdygylIUg0Xb5FSwhb0JlP6NjJooqI1cu6_cKCoZU_fZle-L6XbNuaM=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/QUSvrxGE0CCrmAZ1qOVW9I6qILLHy3uZczk0LUapkpNwbyNHdni5bzatPneY_ztKzWhLN5R4cRfTcwkE_l01dFVOIQlVdP8dqmM4x0K_jNadVcl5ykCAMiFQd0e4wyoYUkvMsPOVyuFJ1Iz5PnLB2r7jkRpNk5vsOUaubJ2bvQHdRHnL6ukn6AP7YS07j513L4YOQTB0xtO5-4IyUVVJCf4v4OQTYHm26w6tSBsBeDoKYKGTqaD9YOCDF66OtgeMphpUOBuc2vh-30iLwJ8m-X_DPjh9aeFARTPT2lGo0UqV2Jm2cZips64_h_c74boKA58oxM9-d8gXCJX2ITByqtxgF_w1AIzIxisQSiSb1fTqntbqSxtkgArFsz8a27_6ce5Wlw6SPX-nyDm0Nl0XYinlAd02YfES1fiWSlN3PmxJTJhqEDzyG7MFnV68eNQZi9J466ZAd4N1rvWMw0LvVHczCOldGVjSqW2RM4EaG2K8aAi3ZjMFq7FR05Y8smDhlKjeYc90Ys-NUZiSS6kcoDWTpu6eMLK-FdyyKoTxmwXv8u9pkhAKGlMZSLzaPs8th4ZRcxdyfO1w-DMe1cZLM97wnlbC1hfJAg3DSnOuBT1W0AOxWzzl29cn5-8i-XzeLn1tMCKZ-kpQ6nJdRsnGK0szLIS5rSpAA-UGOgfQTjWXCaE_pZ0AR5OQWRAAYgbxAc7HnRBl3CAnL3em3eTedcg=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/QZeraCFzbVjAi9dRekQ1aIA1HoxOaUGk8e94ADLRqJrCgC2syoBI90CPLnaCcKTLTlEpsX7nggW2fXOwQtnYpK85Woe3bTaqRPzZEijkHw57teTS1x7HCxRfoM_x4nPkqmXYr2_vM6V1sUWDBIUiUEn4TI8F51W2Gfu7_IhjghyD8hQXa0A_aV1qyCp77V0rskJdQNKQ4lmVmKeqD9qkvRhtCxJq8_vK-hxsSfviuwClLUtnVAYGlrG_nzRrfIdsGYjyjZAdEB_HIcr8AIkzNgoF2M_pLuDdG_eyR_FqBZ7-cOBRzPBBkW2jRjsyhgg69HNB6xqoZuh2-Rnw_VraDkNunhpnOFcG5aoxCQARzepVBKn1A9OLDQQRa0QvBPFlOYqvgCeJUeV2obsBqQnKxmRoAqlnin5tDFXvjQiLkn94fUQPt53YT6Cp--rtxxhdQbXLwJbtSiaBzZNGim5e3pRDHJIYu5sde_UcKEDxep7Uxfei6XjSox-ilDB7h938n81FornkKI-vMmBnzBKjNm6caTE8vCwdkLD6NrZdib5Flf7HGmskA29SUHhAK8nRBWSs1PIGNglV6z6ds3r6vM9rO2XTBAHnrZDqWFm8KYHr5B9rdhHM8A6qj153a1SJUVhFD_Ib6nNPj-aLfS8ta_oTXnHKkWtBm2cUds9AlvSiX8imgMJBk0NWx71OrflGj8E4N9Trf-NY2QpB5Z2TefU=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/dJKbBYXzygCXZokJPfiI6wodrHAGfqgAfY9_Q7YsXWB4qY4xGP8-j2yaJNLZDhyMHrL7xVYKkvMdajfrEntUYhxsjrzusEnTUehoUaa8rdXqSWrjm8NcTJNoAHUXvw6P9zLj9P0dKmBzWxVREhU_DWxwZLzc2tmd1YyNdY3yaaHnguGsU3lrgNL7OmJip1lZvGcCx1Vw8WHCcwe-9jTg-bNj4wS8coxDdD7sYkaiU68uoWZEjYJhWZhB9yXcp_w-VWNJcAuX_I_J3nBmn3XxZK1YS2AolgBZI-7yj6BUb3trDwspJ0GGPeHIMVyVcGB4m7amGznNcq8IloyqF0LcJBSmFl4nERa1NVQFm4RdYdh33MN656rQuai_J-fHNrTA1x-COwpF6qyitRHpB20Inhyejm4o0ycO0DMy2_goeb3KH-EyvNcIlKfbN9S0wwspfzzxr2zMwR8F7MgM-d2rYO13m275B_BgYANDZGjJAFIPC93KJH8GMXFXwkUeTkWZLcRfeplqH_Ay9wiv1sg8_w7UCRbVSlmxdmquqfgUEpIdmPDbABXAeObYuWREVxu3RDjx0inrhknCI7meSKO4cvYpyAeFUimxkjRbnIvoZ-EJ1Kp-UOPPrQMEKX8FjCZCDiOFkWpYjJzsEITuXoxwNMdzoBCcXkNxPx-gb2qn1P4ruqXkj0XRNsGSTgOAHPeKWMHEmsDhzFYUk7Qr7PH21YI=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/SszZXLZcA_lJyz1ylyK7SVniid2vqpLzWsPkM1fhYB_c36bbRbdM0xk7-Pv_IMV9qZjOJpSy897nIfEo2BMeJpujrPdXph6IfG7huXIXsihNm9fV6JjSpA3Tv97kov6MOMLayWgeLs0zxILzR2D6OuVe4Y5OrO4i830aiKQ7zUrACPk-mLC94rNXv3AefuEen_flvq9n3uLbJuCNx0RLoyvuDJGi801WWdeIq6EhO5kWlCB3Hzee1Uhzbg_McdNWj8K7IfmNajee2LbJo8vQLWOlKRvxIsMHncFqgJKj_kLXxRfKe7iDlIOUogt-6WNmb6gFz312Qfx71AZ51Q3wq73vk2x00Xeisnkx_1GCo6twzvtCa7JhdEXkBFslM6NMLb1xWC9KNCkSp316U3mMU2WKosKGdrULWSNySkNKx3nNx0vUh72swHF5oAD4VGdO2xyEKCpF-VZqzha30HyhtK7NXow769aZjdFO0N_MykQLNrRqXhsWPGBCahg507aZx5Tt3AoD088ckORXrK1tItcM8N4dRr8stCu7XWE3w4hIeBP7Fv1D_LIsnALtIgNE6R80QQua1K4qi1V8KEZOvnIZNGydzWfGMg1zyHT46rGyxf_4eBgsj_E45XRBKq5ZWvR-_w4fkmphR6aChn5p8mw3vNbhzvxBn8gHucyBycwb7OAjTk4R6B6dtk_P-L8wjxVrAGDj-dmqCUrNsl1QXwk=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/Ve1AMgyG8v8ju7rx0frn5xpBakwk88kwLGzrNSqt4HMpAk3DGpe0JtPDmz8xp7IepdmLlSbLk43d4QRjy782_tB77B8vd8vsL-b833bM-FSc1ZhNdO4yVIr83xaK8G2y4ING6wM2W6zO7FeHIVMNhxhX3NO92mMk06iKe-iyHz4F2gi5F0hxbJ6vB1XW2jLAC2NhXe_3nuetMXTY959_TxoSNieP_nJ2azhvUeuIEiBNhT0BlrSCMReNobk00Qii167w0anNHC44iAX0BKNsDngn7w2-99n3957NY1qke4FIfC6RbNipXAAgjai0ArlE-ftzW4-25XzjzgaRs7GtpIPOkvJkhpki0TdDRtur5hxiJsBbeCsVhDMJtfYFQ5SBvt7XL5hvp4KOMmWwLpSalHhjpN6NGpS8E8Hg4tIS9u2cUvssPu8eW9dPXeYKAyC_8wBAShXaZhJJ1HrS7IKvLxqFlFuwr35SlrQ8dHyhtmHlFwJZHJfNeOqsRBqHuEUIYfQ0xZ_P_Cz_1RG40u4H1IiGBHlUKkOm1bVWGBLP3T5283QaNy-NoK90XhH02yaYP7VHqYG2QyM74MIhuZe6UFKrN6SNEHSLpf16naoLfP7b9A00pdRur8D6ERZ8YZGn4vLCHsf7pnP6ylYbZITMO1-qhkIQQ74ihJwErt7YoPWu2xqCxIaFZrJtbDz_LB7GA5v8QUfY5tGa-kPU8Qr6zeg=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/bvblpeDClAaMo97-fyMYVOrp1KJhOFauc3z7_HxgmDzURFnh7CW54xcYVfS7ciCCybwJUfA4NqiU8Urh4J_0ssMaAYeN96MynaohRd3mJt0kponycT1FL4I7WGmWKfhmHH00pH-wx9XMGAMMl4_R7_NGiPG-YCOAp_KWaJ5ULfdSrM3LTU5Z3conq4KNp-F-Edhc3vQd5M_Plj_OuBLkYHeBUhelL4FnvGJklOqDgoO6WaK4ZLb_HbgmsrRZYIhbzDxvhonPlzBakTeqZpMGFhYSwqf7aYb3BZ07FzGeWWY27F-iNhCURUk_uzB7iCk_xp9j2paBAaj1on1xYFLZSasQngC8P46dzbayqlA6no82W1q7p6Y6Ywd9Bo19ls4ActxJRJSf3sytKD2yUp1gEhNNSYQxf4U5p5gVmnwFQqnUAEWGutDUEsZqoCQ01HWOEc_ukh-NbWDH_wleCDi_ljXEFyAH6TON_2yyzGP1Vpxf2na3z5p3eiaFAPnJnPWU76XbLYgcA760J_v1jOrrcj5yXXquVpIQB_hm4ncFFis4cjNR1fgqpqjY2XpY8G5biA7iBP8WGhW5gkqB6vsZimHAu-HuX6WiIalAcCtb_M8Dg_Tx9AeHVcips2UtWMBEpSw7exTnRAlwpvTFNwOOlrZ191yVdA5fugY4gdeBjfQaPc7sdE4QgikDDf1-YepZg_Sk0URf270pO0gU02pK6X8=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/nSVTd4KtmA-dD6-yaGW1lT7KDeaHr1TaKLBcgNFPaSkqeenV9-UxdOWYpoIKHzoENPuz-o27SUGfpB3nZsz9Mx_p5RYG7wExvRKaZsy2NZ_vZtXW72FGne4TBMMhdhJTlYRJN4iQtWvd1Xe0Dy9JJb0iZIRm8CmDQiozTiwE4kMnwPdL-9otNG23BMwKuyVtCbPMXfhkPTDSVg_Qdn4fPk9dVkkGeCl9TzRfQ5DrUQzT2TSKbz4eeJgpi0JOnpTBWvAyJ-lNcuWKBIjLZAyXRat2ASaVLFJRGdz1UqyCsmEOFp5m46OaCaGeSEQ-FsHOKFV7JHLCID2X9EzUvUMGwWrSPLNpSh3ifbQrHQfe7_zGVUEGFU9jGprsPHf8kMstxbUV-YEFk2Vwng7e03_c5V1WxGWZEzZi-Ids2-4Xa3FXLvJS2hwbBKAIkbsM4q_YyjjSh2_D77CAfdx2dOLeuS4q4Ihe8dL8CE7EntnFRZsIhNjUB1irV0qDPy7nVJXFHGWKErNFe3h9a0zI8LeioiGYj1HZokqRRSNS_cIYYJ32as8i4tbIfAeIZiMyoGzD4bwCWQsI86bYR0h0R1NLV5tznm_JTigXj5Ojih_Kh00JAnqk3B3WRCvCQdPtGOYE8tNPhwIx4jY0zWKMhhkEpnXYPe39j50OqVz7ZMcb0GNyjUcTz2MfFiovmZo6UdlmzYC3gY80kyfhDtZ5adH5EAE=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/VyclnIm7Ey9bFpGaTApUQJFlmpk_mfOnqpnsAiv7fFZ3MGOKkNEO5pXT3nU6cgVtRXeXczFssseX6d5oREM98xMZJHJjipyXgvZ--pn7uwTEwXN-8QUmxRcwZZ6C7liYDeflxwOS1DfgxcazOxOx75-MN5HTrHbkbFvyWwxl3s-0OD0bpqi69ooQdEQ4Ek0tbj4Oipfg2hz7cZHKa9h-CWqQQINb5SMnaTCsjEVt2Ic4KxXfcPtEnPHqant8GcSDYliZLp8T5_V_XRVdb3dnym9pgaIc9Os6oEUOJBLYcJX3SJW7lZDgTizuI7fXnn8AvdCm5QFgRvgSCXrJ_8KcVjeEfeVWPaZCu2moa2VcbacbDiPKD3KTeJ9UjBCCb1Ftn_sMSyKzN5hFwnhNkiQJc2H8N57jLhUyMSDPNdzNGryG7Lvm61SwxprnpebR1d6DHIiMDoDTEG1rPJ_8_2N-xZ4QkYEQbaN_Q8uVf_WjJuFkE3Y8RSuz9zNvhy7n4d6FauJBe7HC4cKHOj7QGrkdtVKM2KGSwIeTfindJgZxwn5zxs7odeUZS2PwDFmfGzSDYwOzBRPrxjMd0Y_MaguK-rQV19ns-gU4vaStHD6iAd4nwZfUCG3yB-ljEzlXNkSnoVpQSGerifZ0XtleNhsbypWKgNa8Awaaf1PwCtpl73zvs_yN55Ak7aVZ38QrmwlI4rdJa6E4iCWGmmBRv7Lyx5E=w501-h1001-no?authuser=0",
            "https://lh3.googleusercontent.com/1BYp0xIQ2viCO_Odcg2Dmz_UadrK3s3v_dYHTugZWa6iQ_mE8n1-b2uRWR35o0_37vy95RujtSsPkp6eTnbox6D_Taalqr-UqRDfec7Fx2K5M7mpHXCIaZ3oZCfAaRNemcaHC7KjsoWWuzTDtd4hkUbwRirXmiIaUnqKEDz3tmzLCGGYeK86Hmb1LofcvvzSeRUApRYAdM8i50rY3_rnF2GOp4RhVupvGUEQz8hfsyxbdj7H410y2yslJxMAyYJZ2nXGcbsXVNaXOK9AH7UENbxTxVWb6Jg5P4AvPZSzI6xmVjTL0I9vlJnnDscp0b-lerIwaPSBUf5YbRp7WpUDHjG_xb_aIbBYhS1f4EfUzNNhGUT7fEciuD9nsrhzPy14Ph3zyK0K-_196YzRQo9LXoTrqHDajfUSr5mETmZobn0UnjOYYCYz-YizmSedosqtNiO0MmUVMUELiEa2NuX0W1JkTqRwq9YzwmvEp84oOseXy-mOB_qbT_uhQzg18rnoKmRm6WzpPNKoolbWfZqG-POYIPVpOuuzsSspQHB2D5rVnji5H_mTpIEaVm2Kx_UJkFYfwNAHpYaKWUceKSi8Ak3DSGclgZwAn44-jMw7UiE1FTmPPL9DkcnH26ePK3qtE_fazKfxH-OGvmSArHJlGCCTb6yIGekszOexLsAIpKz638LcVekhVeee0r2A0EbhCHi4x2IEVSSecHFfZ7Y5llY=w702-h1402-no?authuser=0",
            "https://lh3.googleusercontent.com/cQKSaIsbg-b-yGs4vhc4Fx_VUKUGtZsM25M-pVC11a2WUd0-FA7cyEnB1DRUr3YLvd_TIjRYc8dd-w8378vnZlB3AEq_eAJcas_A2GqmFDZhRZO0LNcESRafbOyn3eOr37Sn7JBzk6ajAOkL15Y_rXqMXVZ7u-OZgvTmhaffQoDL1lU58nrh_1e5U0FyCxc1RUhjmpE3RQ72YxLA0stpWjKAxS1frM1zT3eX98tK7SFdfz-hEXJrKeVrKs0WK73BJgNitJjDCTbqcMb55hs-uL6QMvN0LPQm1g1vwx6bGQ92n0tDeuU9ndehdmfLO7Qyy943vNp-0FyaLy1n1n5G4k9Frb2YkljhKT0gl6C3gbNmFwYD9hru8qUVzhBqcD4CSgLSX6B_i29HzO_Im8BckXjh0R1h_wi3D9LFHfaDakmJy02fToG2rsHFU1ofmDNWW6Q2Yfrd_rcSMCfupSWUl1c_F6cCkAojk4XydzQ2YMbDIQaNpBP6APppLK4-KdLfHn2Q6BsV3QMNN5dIJio_J-4vdOOmFB-8WRTMKBWZtI1T3kflgwOyCkP7X1vBSSaslzAosUPiylpv0UaJLROpGMVwO_7yMLTPh_Kl8WSwqHQ1MvkVihqWzvVU6WHUJ0Xx-21MWey7s7T-_wBpJg-O0992Jp8VJ06V0P9P6uEN83ojxvkxbvNzxZErhiSmYakrEmUlXTfP-NCbSAGiiQ3UesE=w702-h1402-no?authuser=0",
          ],
          technologies: [
            "Spring Boot (Java)",
            "SQL",
            "Android Studio",
            "Firebase",
          ],
          links: [
            {
              url: "https://www.youtube.com/embed/1wInNwdrN88",
              title: "YouTube video: Timeshare",
              isVideo: true,
            },
            { url: "https://github.com/ahmadalghali/Timeshare" },
            { url: "https://github.com/ahmadalghali/Timeshare-api" },
          ],
        },
        {
          id: "2",
          title: "PropertyPal",
          description:
            "This is a standalone mobile application developed in Android Studio as the assignment of my Mobile Application Development module in final year. The app helps property agents to document properties and other data regarding potential buyers and offers.",
          images: [
            "https://lh3.googleusercontent.com/MLaAb-U5DWAxaN0PZobfCal23p6-EGaD1HCBHVd1eprUkcEu4Xp77vH5WvoWoTCQ8_wXUVzojwypR16DPc_Wr8OGBfKA_o79WFAhR8tdmn-M253YzTU0oA8pV1ci58DHuyP-pwEtNGrwKKQai40J54171dxlnt7UZ7VoIve1VQyvH82ubqYukGoeRNMWImsaO0QXYhftCE4d21s8uqnLrhC2VZn7qz_-AoxHBPknJhQtGLawlycLayjX4W52yjLTR58yhYumB1DmPI_K73bE2BgkBv3FVghGMIIl6zkayvy7BXl2_OsC4O_HLnzPAEOpNQVUP-vh8HD_EqR62yRPM2AsI9kVFBwEqPSJzCeTol5qRxzHa_mGui7iCS_uxyrm0Gvs9t4G-yG3dmHp5U19_81NR3Imy9GrRWP787-DVpBcOvBKBnNKFazLGeRGej0aXHQF1XOk7ZXW-HkuEvXCoQvjHWhIL5bHvdaWIDX-JXQ-Y6V7tmpMMU9yMj-OHPJsAgwWZifzx77VHcNNSti2IQ7zvk-_ZuTr2FxTgc2n5kDDFdrj2zCx5sjjBPy4jTRoYvuVA6IFuP-vACwoP2eFZ8uKdNJRyLb4rB09KjK4nkQP0aXWIjfDhIOM7HzyxtvJ1qkyJuF2IYHV4PDkPAx9DfsOyLqjYj4sjDtMiaqPKaHK0DoCiRBAAHrI4Zh_wKQ4ImyfYoz8URlPPPAzP61Fn-E=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/z8p-0MJz4LAa4uICltYrR-9KFDN1OllYPhUqbbE1aUtWTU-BqrDFtpxmpUPeQf1yDh1mHWqYrJvXb-8EKVhHrogQbL0b_8zliClH1bQn1gkga8S5jn01X53WWP_wNNT_ZOGwWHVwNwczN2210YHNzs-Lje8Um6Fh-6cIhAMpv2S4k3n6GITbO9vsS7x5kYhNICykG9NGp1AUUeMWZqGC22Gre0yDbAcp1k5VraLtfC_JpCsX3vrLWmM5cSPajHKW7FC5N-XRMusX_N_gPgbrDqbtl53nsViq6siIPMbGo8jgkJBEThfex4yH7S_uog4rwUTyrJXK4TUc2Ma95vyv_7yKFP2yXTBZzSKZcDwUmGxDcaRyNSooHcslpN5c_YUfYRTeaWVXSrcHj2gNI2g2E4ITV7I8c0vxjwvPt_CDDwLazDHVjO9M3J3Vczvxtawtvqq-5bKjWw5gae1bkGIjFt7FcdD8dwey8MpUoavIn6hQ7XYLgrW0Odmn1GQv9COpr9ks_MB6KkQAvTajhsgULziUUofMn3XX-gMi3emzNRJSLEYKyXx9DxJAqxi886tIEY83_Et4j6AywUzqbQPYquRymvuOxwmMaOKmsQdnKduJE2eF6amzjL5AztSJk3dflTRCLmlCWWO0rkcrj2sUC6UQLJHyr7xypI9iZnoBcVaJu419CeCavLarveUdXWPSTE7FTMCWlQwCFlyLO1P9gNI=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/FJT66mW9kjNx3TuamhbgAGcAXgKP7s4hPQsEswVpHmWrPlVgjFxMULshAsMjuoXhie5ONqVdANQ4IaeZ4EkVmlV_Ni-nolupYADhgPZcF6sNR_2R2SLJlU9NR5Bl9aAT5AZ9utqmcumLmPVGfvnA8iidd3-VfJyyPnJF5iv_pfPySm3PN921Ant4rSGt58t6zFSge6EU8Bn8foEp9UO_YKAfciDa_558XcCgng_y4hI_vhGAkt3O0kEqCmLr9UNHO5dJbJcxN3512wTBYz9U7SXwwOpugWP4X-pcyaZ0BzAPZjEFxDe5_IiIcssBuqnrMFTrrTfOcKO7_Be-aUJXON0NpeBZ50WXl-uWz2WKg40T5fHRNytiRdiAqIoKX_0GXR0Cm460MwELrh8rY-PUWICit5XqjdejYsIiN5Ksx26NEOaZqu0fMzaxF9Gt3Jzo3lbx3HAHD9OmGv9XgpM2qAZlNSZXveeJfRb2xBRGEJn3qfv0AHh-uiTJ3AVDFmyAH6OelNXW8bo-7vfhseAhcd2ie7CFSoYvaw1WrmcQH6OfhKyfk0E1GcFVkSQPN7pdTn9RmruIWZgFO9tb1ea3hn3W5rYpFBPdX0l7ybf7KX8qGxvvK2HuWnve_PEfXVJXG9H7npxKDFPebeKC4FNGobwHE45QlEnME0tP6FdGYu8QO6Hgqa2gqRi11KkQlszwlAgSfVioX_AC9PPuQTu2hSY=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/sfOfLg8fAvmKsH2wLmjW-Z23zNxnwYL8mbi6MRa3NNCUrTRSBIYv1toLJhlzwKDEgIKqr3ueKdFbBh9ZYEXzYGqaJd5hmBQqhdsjpv44lUxSlGcONlhsyBZopbjVETl-bQAZ6CDoqgfrdKmm-7RBhO2ijaNm04JgfP6Bd69a5O-KO10KRc3JRalMF6wK9MEW-WBKBEw7a9i-0bcSK4XEKGhUNF8TAQc0u1OPuJ-2vpkSE3XykCkTJQ1aS828xtz5rE3qXyTa03WuayRg-gz6_shN39zzwuX194RuUE7Vm2MraIV1ibImySDdOywOE7Q6yIoPH-qmBTBQWH2Bkmh_tLIoZXewNKYN9lxgP9V2eIrNsX62B6PzE9sPO4oL2nDFJ2u0K7pZ49Rf5to_afPX3ZClnThHyleqjJUh0CO1VUfYrkUltVoxFdVJmlwpWFBe4hY8iesyb7iSWGL1rLZJcHh41Q5z7d6ngHrPNpf6HiVpfgNulvKT3Dln6HAUjI_EmcWNn_azT7tXvL0QZQ44cztXTHYk09wdcRWOYBsvLRA9oi_2avwvAx2H-o5je3t0u7RlgsKH_htRY6qD4kP0LQqv47u2Wo3AuuWUkRu4fv3DG5teWX5InUinOS3HjskobdUJyy4yGLCoWj9ReduMsXBlz4NJOaw5yEHNOZwTYa9GT-5wEPnGHBUujut6JGvJrbaObk1ykihh_tgXTo6pXCU=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/Vz40ZCsOr1caYDD0T8-0JKFDBY173w13nLVxsk9DG8r1zgStBjz7s6g7SDpgqmyjK2gbtrhKufoQEGltt_tSGCbMStx0tbl-GjQryKYIYW0Qevcvb9avsKteEiqpO-du8x42goitVtCNVidI0IWatYggv-QXnYYrOq-SjkYym6-m-lh4SdqtW9aJRz-X1jQdFGX1vcvC1w4xALJnlcgpfDIQCNm5pyZLg5yHxNgK_AKGaCI9Z-Oix4RyWmg8B2IoNoWng8mQ-FecnYFlkIInBnIpFuOm7ojGlAhnDA2AXy8pK1Ksuf6sKDt_dlRCmss3ghCMZr6js2bv8Ij1NNAcHdsuZmbpu36kXxQC3bX0F4aiB0mH-tonyQb9ZpZUW8imLkkFBuNIMCbSnFKqgnuK3zt9OpI3P5Q9sLj4QYEFEwrGeBm7rPAxItLJA805cVwScuErX1HoeJ2nrdTxZrdykprvI56xXimrW2cQPAe9YQF_OUTWuK4wEh1R1AV3iokulUwwmspwZx3l1SNM5dlVC3vto8lw80kjkA1ZO7MJdOuX_TqNJAXFYJ1HApdczxZltdOKUSxhTehsoh6HpL8gnp8HI31BbLSlN5qtZ1WgF-CUfcZ3hreHaBBKqfDgQqR8XB9L7WYneQdybiej6hmU46_yzxE54Lo8DHgCEOcguJybSTX5yT8oJ9U0SFPwGSUHJ3AfEZ2_QxzMy4y_tmxgFhk=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/dqCyB4A6JzWVcQGlCoiRdFGaSkDg5pVx0AfRDbbShZZOJFogA6aUAJlzIMUyjj1QGfVUjZflFM04gYne1LapOQtQz4VQho5cVmyB1_ST70j3DbqqihkuWnP08buLEmPk-wqS73W5f7R8thftSEmADUm50inHnZCEFjKFlJ7yc0uqOFgDOdXSc86v67Isfdm2ZzY3RW5gIK1GMuUQWXXRDMjDOx_63k5rQi4X4x7U180ldSzyH3eZ2AN7vzaMf2OCf2jgEMvabLXz0L4XDsQonrRcE0mA1R5pNzSS2c_yv_iYUGLXdCeVHbzL93ogE6SE6WUXInhIqVpToAgn94-XnnjKAoaeFys8OIshHMF2v1l9FmEOBSy4N3cElXTCXzAOu8dYyYZHHAFVItG3MqCgTVCf81n6KpQo-ADcRNAyzjAWZwKvIzsqjwAIu_1zkZ25P5ZdmraY0HPAsNWWwy5PjL_XADs2J66R4AKCjwK0MBcDBwwjd7O00FDVY_QdQTDWZ9x13C3hUHn7GUGWq-eqe1YCWAIXtLa3qxDas-kkdRewNl0Fl543EX-E4r4l9RaLUEmiSmWpMEdWRfepRDR4QmZuVQxjNWY5HFwjAqLa4AghGS1ZzCRd9kmc1AGzVCW90RhD4IkVCyc8YykxrgWa1jeMXffxqzA7o5H5Za_-uihLNGhKU-FDgd3R2JJFfrCJfdIAzWTgms0EP5eBeVNpVCs=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/OKUSpPwioH3lPcjyh7tl0x_2KhIei8bEJA7z8ycbZTusTqC_k7whgbYRaUANxJVdPlABNK34WLRGFfUM2vYVIZIzEkzMXRhU-lYuSn57Z5XLYts_wPXv0UVJn6s0mQKkWKFLBXDBBl0KPn1E2FYFHTfWdpb0CRFmHsnFq63u8e89SB2Uhw6DNRrdCoHgN9ha9q5Xx14pWjtoIwO73PxpSJ-Fu83Y0ohDkToWvFMoPrvU5knL5Ba8Pq1GZBVQtiWJEk30b-GJ3kN-1motqtU_TfS2Oq7txuo-02xKWDNkouSHXHCZ17u-8lvIEzFcDRlL6MBoy5e3qhT7iVdrgb5GQ4V6Ds1WGWSTMGES9KEQq8NP13h_pCIxzMUGpWFkPC82Ls91VIKT-fzS9_N1B1IkZieLBnuN7rjv2uIu6QkwKBwbcxGiZX5r6g_QGUukPaPeTJYhhfBjhdBsMKg0rdnQXdlsxOZPdNTcX8jZsq-RgTWUpBRsPHI_ptOwlZrURzTYgRisMMjtRG3tFdvedgvniAcE-MtM0F9Ej7GKaBruMreEsFauixcjqfYTLURe5lMuA8LupeeVkjKSImg1-jN45FKa9RGjkY_i__W090VKTOPtyjaCQXFSTrSVnRS9_5PkHx6ZQjS_fEbPAZNkX9GFhPaWUaiJ14DdYtPxBcV703xFCKdqn90c-lioB9vb7rhUK6VnAGt0G-4dhht-lgFToTI=w796-h1592-no?authuser=0",
            "https://lh3.googleusercontent.com/1blOvdHqjpU1IlV0DJV3gPI_mwQFlCEuqsSaIJ3l-cS-NGkQoIe8OkhXmE7WlyJsJf93-ZfP6_dOZc9dto_a09scXxRxoq3VDxa_DB_ndHy_Rq9b8krXYnTSRj-yz4vslrN6mhZeZfS_8EBiu8J3unFLZT6gKzHt22nj066IpEtvStSPC67xJ4HreJ_xB3E_2Zo7h5i2WL9lUd4O220_xVoW2GCw-2q3KNnHqPttt6f7Tatg4wKGfQj-mveCVP4vXYWEX_u8drMSuQyYCULQR5jIfM3cTDnkNSAQlV24d7W1UTkq4b36rB2lbM1i_1-TTnIv2vEtQuNLI2txzdSDAlo0x66_9Qk9HfEPIIGrZHBt_OASSFJSDHM0OYe8q_jNnYsXdtwys16OBcvYFfEFwI3CpWgAkBDG0Zmojo8mH-gYHtnuP7luJNg8_snKY04tasdSX7Si54xUqLcd5H8ngeKFhdn3-lrnZ9j8z58bU-sLl42nAYk6ZuNg4_v4rotM3N4Fk5j83kVjby-kRweRAil9cclmK9ZrZCOQRviLFXJR0fgloSVnQPcjJe28y2OHeS46fcinSFPnQ-PZwJTsygb_KrnTQGhTfsoYm8JTJGLF4lbRzpWM3WeS-JemRFzm5A362cbSDOqUE7oKVbbm2Y1Dh9wqZdVMuRYX4w7kqmqfhOXVMsVq-7Gvp2pGR5XhOFEaFpslMmAAYNV-fTDsGGg=w796-h1592-no?authuser=0",
          ],
          technologies: [
            "Java",
            "SQLite (Room)",
            "Android Studio",
            "Cordova (PhoneGap)",
          ],
          links: [
            {
              url: "https://youtube.com/embed/6BuefvYEAUc",
              title: "YouTube video: PropertyPal",
              isVideo: true,
            },
            {
              url: "https://github.com/ahmadalghali/PropertyPal",
              title: null,
            },
          ],
        },
        {
          id: "3",
          title: "TheUniBook",
          description:
            "As part of our coursework specification for Enterprise Web Development module in final year, we were to get into teams with each memeber having specific skills and together we were to adopt an Agile Scrum approach by using Kanban boards, user stories, planning poker and daily standup meetings. \n\n The specifcation required the developement of a secure web application for universities to use a platform for idea suggestions, all general staff can contribute by sharing their ideas that can be upvoted and commented on. It is also a role-based system which incluedes a QA Manager, QA coordinator, System administrator and general Staff.",
          images: [],
          technologies: [
            "Spring Boot (Java)",
            "SQL Server (Azure)",
            "HTML, CSS & JavaScript",
          ],
          links: [
            {
              url: "https://youtube.com/embed/zrjPQFqCOCI",
              title: "YouTube video: TheUniBook",
              isVideo: true,
            },
            {
              url: "https://github.com/ahmadalghali/TheUniBook",
              title: null,
              isVideo: true,
            },
            {
              url: "https://github.com/ahmadalghali/TheUniBook-api",
              title: null,
            },
          ],
        },
        // {
        //   id: "4",
        //   title: "ahmadzon",
        //   description:
        //     "A personal hobby project currently under development in my spare time, it is aimed to be an amazon ecommerce clone, hence the name.",
        //   images: [],
        //   technologies: [
        //     "Spring Boot (Java)",
        //     "MySQL",
        //     "HTML, CSS & JavaScript",
        //   ],
        //   links: [
        //     "https://github.com/ahmadalghali/ahmadzon",
        //     "https://github.com/ahmadalghali/ahmadzon-frontend",
        //   ],
        // },
      ],
    };
  },
  methods: {
    async getProjects() {
      let projects = await fetch("../data/projects.json").then((res) =>
        res.json()
      );

      console.log(projects);
      this.projects = projects;
    },
  },
  computed: {
    isFirstElement(index) {
      return {
        active: index == 0,
      };
    },
  },
  mounted() {
    // this.getProjects();
  },
};
</script>

<style scoped>
.project-description {
  font-size: larger;
}

ul li {
  font-size: 18px;
  list-style: none;
  /* margin-right: 50px; */
  /* display: inline; */
  margin-bottom: 20px;
}

.carousel img {
  display: block;
  max-height: 600px;
  max-width: 300px;
  width: auto;
  height: auto;
  margin: auto;
  cursor: pointer;
}

.project {
  margin-bottom: 200px;
}
/* .item img {
  position: absolute;
  top: 0;
  left: 0;
  min-height: 300px;
} */
</style>
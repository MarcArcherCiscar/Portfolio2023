<template>
    <article class="resume active" data-page="resume">

        <header>
          <h2 class="h2 article-title">Resume</h2>
        </header>

        <section class="timeline">

          <div class="title-wrapper">
            <div class="icon-box">
              <i class="pi pi-book" style="font-size: 1.5rem"></i>
            </div>

            <h3 class="h3">Experience</h3>
          </div>

          <ol class="timeline-list">

            <li class="timeline-item">
              <h4 class="h4 timeline-item-title">Full stack & mobile developer</h4>
              <span>2021 — Present</span>
              <p class="timeline-text">
                In my current role, I design and implement web and mobile applications using technologies like Vue, Symfony amd Jquery. I have successfully integrated third-party APIs and optimized applications for performance and scalability.
              </p>
            </li>
            
            <li class="timeline-item">
              <h4 class="h4 timeline-item-title">Full stack & mobile developer</h4>
              <span>2020 — 2021</span>
              <p class="timeline-text">
                I developed and maintained web and mobile applications, working with cross-functional teams to meet business objectives. I ensured well-structured and maintainable code, and contributed to enhancing user experience.
              </p>
            </li>
            
            <li class="timeline-item">
              <h4 class="h4 timeline-item-title">Navision Programmer</h4>
              <span>2019 — 2020</span>
              <p class="timeline-text">
                I specialized in customizing and optimizing Microsoft Dynamics NAV (Navision) ERP systems, developing custom modules and reports, integrating third-party applications, and implementing automated workflows. I provided training and support to end-users.
              </p>
            </li>
          </ol>

        </section>

        <section class="skill">
          <h3 class="h3 skills-title">My skills</h3>
          <ul class="skills-list content-card">
            <li class="skill-item" title="Ionic"><img src="../assets/images/skills/ionic.png" alt="Ionic" width="40"></li>
            <li class="skill-item" title="Symfony"><img src="../assets/images/skills/symfony.png" alt="Symfony" width="40"></li>
            <li class="skill-item" title="Laravel"><img src="../assets/images/skills/laravel.png" alt="Laravel" width="40"></li>
            <li class="skill-item" title="Yii"><img src="../assets/images/skills/yii.png" alt="Yii" width="40"></li>
            <li class="skill-item" title="Vue"><img src="../assets/images/skills/vue.png" alt="Vue" width="40"></li>
            <li class="skill-item" title="React"><img src="../assets/images/skills/react.png" alt="React" width="40"></li>
            <li class="skill-item" title="Angular"><img src="../assets/images/skills/angular.png" alt="Angular" width="40"></li>
            <li class="skill-item" title="Mysql"><img src="../assets/images/skills/mysql.png" alt="Mysql" width="40"></li>
            <li class="skill-item" title="Solidity"><img src="../assets/images/skills/solidity.png" alt="Solidity" width="40"></li>
            <li class="skill-item" title="Rust"><img src="../assets/images/skills/rust.png" alt="Rust" width="40"></li>
          </ul>
        </section>

      </article>
</template>

<style>
  .skills-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    list-style-type: none;
    margin: 0;
    width: 80%;
    margin: 20px auto;
  }
  .skill-item {
    flex: 0 0 calc(20% - 8px);
    margin-bottom: 16px;
    text-align: center;
  }
</style>
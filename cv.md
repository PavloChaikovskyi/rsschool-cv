## [rsschool-cv](/rsschool-cv/cv)

# Pavlo Chaikovskyi

## Front-End Developer (JS/React/TS)

# Contact information: 

* **Address:** Poland, Cracow 
* **Email:** [chaykovskiypavel@gmail.com](mailto:chaykovskiypavel@gmail.com "mail me")
* **Phone:** [+48577187909](tel:+48577187909 "call me")
* **Linkedin:** [PavloChaikovskyi](https://www.linkedin.com/in/pavlochaikovskyi/ "My linkedin"){:target="_blank"}
* **Codewars:**  [PavloChaikovskyi](https://www.codewars.com/users/PavloChaikovskyi "My Profile on CodeWars"){:target="_blank"}
* **GitHub:** [PavloChaikovskyi](https://github.com/PavloChaikovskyi "My GitHub"){:target="_blank"}

# About

I'm Front-End developer with 2 years commercial experience in creating custom web-sites on WordPress CMS,  
using PHP, HTML, SCSS, JS, TWIG, Bootstrap, Gulp, Git and others tools. Currently I'm learning TypeScript and   
React, because I want to create a web applications.  
My last project during working in Kerris Group: [https://cylindersi.pl](https://cylindersi.pl "Warsaw car-sharing company")

# Stack Details

* Creating fully responsive websites
* Focus on the highest quality of coding
* Using Guttenberg and ACF Blocks
* Implementation of external REST APIs
* Creating custom solutions
* Use reusable components
* IT CSS Method and preprocessor SCSS with BEM
* Website optimization to achieve great scores
* Work on Local Environment
* Deploying Projects to Production
* Experience of using Version Control System (Git) in console
* Use DRY methodology
* Working with project management tools (Jira, Clickup, Asana)
* Working with graphical tools (AdobeXD, Invision, Figma, etc.)
* Using of project building tools (Gulp, Webpack)
* Using Node.js with NPM
* Experience of working in code reviews mode
* Using IDE VS Code (experience with WebStorm)
* Prefer working on MacOS (experience with Windows, Linux)

# Code Example

This module responsible for automate  checking if insta token expire data coming,  
if yes, creating request for generating new Instagram Token, and rewrite it do DB with new expired date. 

```js
const refreshInstaToken = () => {
  // GET TOKEN FROM ACF
  var url = `https://graph.instagram.com/refresh_access_token?grant_type=ig_refresh_token&&access_token=${instaToken}`;

  const today = new Date().getTime() / 1000;
  // console.log('today:', today)
  // console.log('instaTokenExpired:', instaTokenExpired)

  function setTokenDB(token, time) {  
    const item_form = new FormData();
    item_form.append('action', 'send_new_instatoken_data');
    item_form.append('tokenInst', token);
    item_form.append('instaTime', time);
    fetch(ajaxUrl, {
      method: 'post',
      body: item_form,
    }).then(response => {
      // console.log("second Ajax:", response);
      console.log('Insta token was refreshed');
    });
  }

  if (+instaTokenExpired <= today) {
    fetch(url, {
      method: 'get',
    })
    // get response with new expired time and new insta token
      .then(response => response.json())
      .then(response => {
        // console.log('response first ajax:', response);
        // console.log(ajaxUrl);
        if (response.access_token) {
          let newExpiredDate = response.expires_in + today - 1209600; // expires date = response (seconds to expired ) + today(in seconds) - 1209600(2 weeks); 
          setTokenDB(response.access_token, newExpiredDate);
          // console.log('newExpiredDate:', newExpiredDate)
          // console.log(response.expires_in);
        }
      });
  } else {
    console.log('Instagram Token is active');
    console.log('expired after:', ((+instaTokenExpired + 1209600 - today) / 24 / 60 / 60).toFixed(), 'days');
  }
};

export default refreshInstaToken;
```

# Commercial Experience

Mar 2022 - Present  
[Cognizant][https://www.cognizant.com/pl/en "home page"] · Full-time  
Senior Process Executive  
Cracow, Małopolskie, Poland  

2021 [Kerris Group](https://kerris.pl/ "home page")  
Front-End Wordpress Developer  
Fully Remote  
* WordPress : Twig + Gutenberg Blocks;
* Creating fully responsive websites
* Creating custom solutions

2020 [RedrockS – Agencja Kreatywna](https://redrocks.pl/ "home page")  
Junior Front-End Wordpress Developer  
Partly Remote  
* creating custom templates on WordPress CMS;
* creating custom JavaScript solutions;
* cooperation with designers team;
* customer support;

# Education

Bachelor’s Degree, Computer Science  
National University “Lviv Polytechnic”  
Ukraine, Lviv 2015  

# Languages

* English B2 (currently working in international environment)
* Polish Fluent
* Russian Fluent
* Ukrainian Native
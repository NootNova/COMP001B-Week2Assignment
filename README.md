
Author: Nova Wolta
Purpose: Work for the COMP001B Week 2 assignment.

# comp1b-m02-assignment

## This starter is for one task only

Course: COMP1B. Module 2. Task: assignment.

Use a NEW folder and NEW GitHub repository named `comp1b-m02-assignment` (or an equally clear unique name). The lecture activity and coding assignment must have different repository URLs. This ZIP contains only this task’s project.

## Goal and scope

Measure the 240px content-box and border-box states, record content/border-box/margin footprints, compare display modes, and leave a flexible card tested at 375 and 1024px.

Follow the matching Canvas directions and existing rubric for the precise required evidence. The activity is required/ungraded; the coding assignment/draft/final uses its existing rubric. The starter is scaffolding, not a finished solution.

## Open and run

1. Extract this ZIP. Open the `comp1b-m02-assignment` folder containing index.html in VS Code, rather than the ZIP or a parent folder.
2. Root files supplied: index.html, main.css.
3. Open index.html in a browser; save and refresh after source changes. No npm packages or build command are required.

## Source record

- Starter: comp1b-m02-assignment-starter.zip

- Earlier work copied: https://github.com/NootNova/COMP1B-Week2Lesson  [Grabbed the CSS code for the article-card class, badge class, page-wrapper class]

- My own changes for THIS task: [explain]

## Measured box model

Write actual observations in this README.md. Replace placeholders with your results, including failures and limitations. A planned test is not a completed test. Add rows as needed; a check that found no defect should say so honestly. The matching Canvas task defines the work due at this stage.

| Controlled state | Content width | Border-box width | Outside left / right margins | Total horizontal footprint | Prediction and measured result |

---------------------------------------------------

| 240px content-box | 240px | 276px | 12px - 12px | 300px | My Predictions with the content-box come from how the padding and border are outside the content which means the declared width is the content width (240px). The padding and border are added to this number twice, once for each side (left & right) [16px x 2 = 32px] [2px x 2 = 4px] 32px + 4px + 240px = 276px. The margin is outside of this and is added twice to find the total horizontal footprint, [12px x 2 = 24px] 24px + 276px = 300px |

| 240px content-box acutal | 240px | 275.2px | 12px - 12px | 299.2px | the border issuse is taking another 0.8px from the total footprint.

---------------------------------------------------

| 240px border-box | 204px | 240px | 12px - 12px | 264px | My Predictions come from a base width of 240px, this being declared "border-box" the stated width is the max the width of the Content, Padding, and Border can extened to. This means that because the border-box width is the stated 240px, the content width is found by subtracting by both sides of the padding and border from this number, they are set to 16px(32px for both sides) and 2px(4px for both sides) respectively, the math is 240px - 32px - 4px = 204px. The margin is set outside of those calculations but plays into the total horizonatal footprint, the left and right margin are 12px each and when added to the border-box width (240px + 12px + 12px) give the total horizonatal width of 264px.

| 240px border-box acutal | 204.8px | 240px | 12px - 12px | 263.2px | Note: The border issuse from the lesson is still carrying over and is causing my toatl footprint to miss 0.8px.

----------------------------------------------------

## Display and flexible-card evidence

Block / inline / inline-block comparison: Block and Inline-block both give the content extra horizontal value where as Inline keeps the content to the size of the text. The Padding, Border, and Margins are untouched from any of the display declarations. This is because any of the "Block" declarations make a "Block" element and those always occupy the full available width.

Final flexible-card choices: 

The page wrapper class having the CSS:     

    max-width: 70rem;
    
    margin-inline: auto;
    
    padding: 1rem; 

And the article card having:

    box-sizing: content-box;
  
    width: 100%;
    
    max-width: 38rem;

    padding: 1rem;

    border: 2px solid #17324d;

    margin: 0 0 1rem;

is what is going to be kept because capping off the max width to avoid over expanding for smaller veiw ports and having margin inline set to auto helps with keeping the content stable and felxable.

----------------------------------------------------

| 375px | The Article card rolls over the right side | fixed Article card to border-box to help with the border running over the right side | No issuses after the fix |

| 1024px | No issuses to report with the veiwport |

| CSS validation | No issuse to report |

----------------------------------------------------

## Independent transfer check

Answer the new case in the matching Canvas assignment. Predict before using the inspector; explain the rule behind your answer, then record your own measured test and correction.

- Case and conditions: [identify the assignment case]
- Prediction and calculation: [your reasoning]
- Inspector observation: [actual values and behavior]
- Minimal correction and reason: [your proposal]
- Retest and explanation: [actual result]

Temporary inspector experiments do not replace the assignment's final saved flexible-card CSS.

## Predictions and actual tests

Write actual observations in this README.md. Replace placeholders with your results, including failures and limitations. A planned test is not a completed test. Add rows as needed; a check that found no defect should say so honestly. The matching Canvas task defines the work due at this stage.

| Action / input / conditions | Prediction before running | Actual before change | My change or none | Actual after / explanation |

----------------------------------------------------

.article-card {

  width: 280px; 
  
  padding: 20px;
  
  border: 3px solid;
  
  margin: 12px;
  
  box-sizing: content-box;

}

PREDICTIONS =

| Content width = 280px | Border-box width = 280px + padding x2 (20px + 20px) + border x2 (3px + 3px) = 326px | Outside margins = 12px left / 12px right | Total horizontal footprint = 326px + left & right margin (12px + 12px) = 350px

ACUTAL = 

| Content width = 280px | Border-box width = 324.8px | Outside margins = 12px left / 12px right | Total horizontal footprint = 348.8px | The border missing a 0.6px on left and right us causing a drop of 1.2px from the total horizontal footprint

----------------------------------------------------

Inspecting the values shows an overlap of the margin shooting vertically over the parenent.

I want to change the box-sizing to border-box. [This is like the issuse I had with the right pushing out past the veiw port and by forcing the padding and border to confine to the set width it should help with the problem.]

after switching it, it got shorter but didn't fix the problem.

I threw a display inline-block onto the article card and it has the card fitting the parent with the margin right along the parents horizontal footprint. This worked because switching the content to an inline forces it to fit into the parent and the block keeps it together.

| 375px | No issuses to report, fits the parent and the veiwport |

| 1024px | Again, no issuses everything fits; No rollover. |

## Submission checklist

- [ ] My source and README belong to this task’s separate folder/repository.
- [ ] I saved, committed, pushed, and opened this repository on GitHub to verify the files.
- [ ] Repository URL: [THIS repository]
- [ ] Live GitHub Pages URL(s), when required: [THIS project’s deployed URL(s)]
- [ ] I submitted THIS repository URL to the matching Canvas item using Website URL and checked the submission confirmation.

Activity Text Entry remains available only as described in the Canvas directions. A push or deployment does not submit Canvas work. Future-use drafts have no current submission or deadline until activated.

## Academic integrity and privacy

AI-assisted or AI-generated content is prohibited. Complete and explain your own work under the existing course policy. Do not include keys, credentials, tokens, or private settings. Preserve the supplied license and identify reused material.

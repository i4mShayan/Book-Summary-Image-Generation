# Book-Summary-Image-Generation
## Description
Imagine capturing the essence of a book in a single image! This project tackled the challenge of processing summaries from a massive dataset of `16,559` books. The goal? To automatically generate images that reflect the vibe of each book.

## Project phases

| Phase | Description |
|--|--|
| [*Data Preprocessing*](https://github.com/i4mShayan/Book-Summary-Image-Generation/edit/main/README.md#1-data-preprocessing) | Cleaning and standardizing the raw data |
| [*EDA*](https://github.com/i4mShayan/Book-Summary-Image-Generation/edit/main/README.md#2-exploratory-data-analysis-eda) | Exploratory Data Analysis |
| [*NLP*](https://github.com/i4mShayan/Book-Summary-Image-Generation/edit/main/README.md#3-natural-language-processing-nlp) | Using Text summarization model to condense the book summaries |
| [*Vision*](https://github.com/i4mShayan/Book-Summary-Image-Generation/edit/main/README.md#4-computer-vision) | Using Text-to-image model to generate books images |
| [*Sample Output*](https://github.com/i4mShayan/Book-Summary-Image-Generation/edit/main/README.md#4-computer-vision) | 20 Sample Outputs |

Here's a quick breakdown of each phase. For a deeper look, check out the details in the notebook!
## 1. Data Preprocessing
In this step, the [raw crawled data](data/booksummaries.txt) of book titles and summaries is cleaned and transformed into a format that is suitable for analysis and the NLP model.
This involves removing duplicates, handling missing values, and standardizing the data.

## 2. Exploratory Data Analysis (EDA)
This step involves exploring the data to gain insights and the size of summary tokens.

The challenge here is to find the best parameters for the Text summarization model.


| Overview | Inliers |
|--|--|
|![image](https://github.com/i4mShayan/Book-Summary-Image-Generation/assets/29325256/f692a3f1-d361-44fb-91ef-667699d0289d) | ![image](https://github.com/i4mShayan/Book-Summary-Image-Generation/assets/29325256/ebacd2a2-fcec-4668-9789-ccaa836e75e3) |

## 3. Natural Language Processing (NLP)
The NLP model is used to condense the book summaries to make them suitable for the Text-To-Image model.

The most effective model discovered for the task of summarizing long texts in our dataset is [a fine-tuned version of LongT5](https://huggingface.co/pszemraj/long-t5-tglobal-base-16384-book-summary), Which is an encoder-decoder longT5 model that is trained using book summaries.

![image](https://github.com/i4mShayan/Book-Summary-Image-Generation/assets/29325256/cec9a38b-fb31-45d3-b986-1e83a63bc90f)

## 4. Computer Vision
Finally, in this step, images of condensed summaries are generated.
I decided to use [SD-XL 1.0-base model](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0) which was a pretty accurate model for the condensed summaries.

![image](https://github.com/i4mShayan/Book-Summary-Image-Generation/assets/29325256/ee9927d9-7906-404e-910f-9c8b51cee48d)

## Sample Output:
Click on each image to see it in its actual size.

<table>
 <tr>
  <td>
   <div style="text-align:center">
    Book of Micah
   </div>
   <img align="center" alt="4452_Book of Micah_nan.jpg" src="./images/4452_Book of Micah_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Jonah
   </div>
   <img align="center" alt="4451_Book of Jonah_nan.jpg" src="./images/4451_Book of Jonah_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Animal Farm
   </div>
   <img align="center" alt="620_Animal Farm_George Orwell.jpg" src="./images/620_Animal Farm_George Orwell.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    A Clockwork Orange
   </div>
   <img align="center" alt="843_A Clockwork Orange_Anthony Burgess.jpg" src="./images/843_A Clockwork Orange_Anthony Burgess.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Blade Runner 2
   </div>
   <img align="center" alt="4082_Blade Runner 2_ The Edge of Human_K. W. Jeter.jpg" src="./images/4082_Blade Runner 2_ The Edge of Human_K. W. Jeter.jpg" width="150px"/>
  </td>
 </tr>
 <tr>
  <td>
   <div style="text-align:center">
    An Enquiry Concerning Human Understanding
   </div>
   <img align="center" alt="1756_An Enquiry Concerning Human Understanding_David Hume.jpg" src="./images/1756_An Enquiry Concerning Human Understanding_David Hume.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    A Wizard of Earthsea
   </div>
   <img align="center" alt="2890_A Wizard of Earthsea_Ursula K. Le Guin.jpg" src="./images/2890_A Wizard of Earthsea_Ursula K. Le Guin.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Ezra
   </div>
   <img align="center" alt="4332_Book of Ezra_nan.jpg" src="./images/4332_Book of Ezra_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Blade Runner 3
   </div>
   <img align="center" alt="4081_Blade Runner 3_ Replicant Night_K. W. Jeter.jpg" src="./images/4081_Blade Runner 3_ Replicant Night_K. W. Jeter.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    A Fire Upon the Deep
   </div>
   <img align="center" alt="2080_A Fire Upon the Deep_Vernor Vinge.jpg" src="./images/2080_A Fire Upon the Deep_Vernor Vinge.jpg" width="150px"/>
  </td>
 </tr>
 <tr>
  <td>
   <div style="text-align:center">
    Book of Hosea
   </div>
   <img align="center" alt="4449_Book of Hosea_nan.jpg" src="./images/4449_Book of Hosea_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Job
   </div>
   <img align="center" alt="4386_Book of Job_nan.jpg" src="./images/4386_Book of Job_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Haggai
   </div>
   <img align="center" alt="4454_Book of Haggai_nan.jpg" src="./images/4454_Book of Haggai_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    The Plague
   </div>
   <img align="center" alt="986_The Plague_Albert Camus.jpg" src="./images/986_The Plague_Albert Camus.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Joshua
   </div>
   <img align="center" alt="4331_Book of Joshua_nan.jpg" src="./images/4331_Book of Joshua_nan.jpg" width="150px"/>
  </td>
 </tr>
 <tr>
  <td>
   <div style="text-align:center">
    Book of Numbers
   </div>
   <img align="center" alt="4376_Book of Numbers_nan.jpg" src="./images/4376_Book of Numbers_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    All Quiet on the Western Front
   </div>
   <img align="center" alt="2152_All Quiet on the Western Front_Erich Maria Remarque.jpg" src="./images/2152_All Quiet on the Western Front_Erich Maria Remarque.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Esther
   </div>
   <img align="center" alt="4382_Book of Esther_nan.jpg" src="./images/4382_Book of Esther_nan.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Anyone Can Whistle
   </div>
   <img align="center" alt="2950_Anyone Can Whistle_Arthur Laurents.jpg" src="./images/2950_Anyone Can Whistle_Arthur Laurents.jpg" width="150px"/>
  </td>
  <td>
   <div style="text-align:center">
    Book of Ruth
   </div>
   <img align="center" alt="4381_Book of Ruth_nan.jpg" src="./images/4381_Book of Ruth_nan.jpg" width="150px"/>
  </td>
 </tr>
</table>

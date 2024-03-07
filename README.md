# 𝕏-Insight💡: Data Scraping, Analysis, Image caption and More

[中文指引](README_zh.md)

This project enables you to fetch liked tweets from Twitter (using Selenium), save it to JSON and Excel files, and perform initial data analysis and image captions.	

This is part of the initial steps for a larger personal project involving Large Language Models (LLMs). 
Stay tuned for more updates!


### Example of Exported Excel sheets & Visualizations:

![Sample Images](images/sample_excel_with_data_viz.png)

## Demo Video

[Demo](https://www.youtube.com/watch?v=UA35W-aWQZk)

## Prerequisites

Before running the code, ensure you have the following:

- Required Python libraries (listed in `requirements.txt`)
- Get your Twitter auth token (Not API key)
  - Quick text instruction:
  - - Go to your already logged-in Twitter
    - `F12` (open dev tools) -> `Application` -> `Cookies` -> `Twitter.com` -> `auth_key`
  - or follow the video demo in FAQs section.
- GEMINI API key (*Optional, only needed if you want to try the image captions feature)

## Setup

1. Clone the repository (Recommend) or download the project files.
   
```
git clone https://github.com/jerlinn/X-Insight
```
  
2. Install the requirements:

```
pip install -r requirements.txt
```

3. Open the `config.py` file and replace the placeholders with your actual API keys:

- Set `TWITTER_AUTH_TOKEN` to your Twitter API authentication token.
- Set `GEMINI_API_KEY` to your GEMINI API key. [🔑 Get your own key here.](https://aistudio.google.com/app/apikey)

## Data Ingestion

To fetch data from Twitter and save it to JSON and Excel files, follow these steps:

1. Open `twitter_data_ingestion.py`.
2. Modify the `fetch_tweets` function call at the bottom of the script with your desired parameters:

- Set the URL of the Twitter page you want to fetch data from (e.g., `https://twitter.com/ilyasut/likes`).
- Specify the start and end dates for the data range (in `YYYY-MM-DD` format).

3. Run the script by executing the following command (recommend run this in IDE directly):

   ```
   python twitter_data_ingestion.py
   ```
4. The script will fetch the data from Twitter, save it to a JSON file, and then export it to an Excel file.

## Data Analysis

To perform initial data analysis on the fetched data, follow these steps:

1. Open the `twitter_data_initial_exploration.ipynb` notebook in Jupyter Notebook or JupyterLab.
2. Run the notebook cells sequentially to load the data from the JSON file and perform various data analysis tasks.

Some sample results:

- Visualizing likes by media type over time
  ![plot](https://github.com/jerlinn/X-Insight/assets/91647085/9ae9f0f7-93c0-46f4-92db-37d35d5ef2ab)
- Creating a calendar heatmap of liked tweets per day
  ![Number of Liked Tweets per Day](images/liked_tweets_per_day.png)

3. The notebook also demonstrates how to use the Gemini API & Replicate API with LlaVa V1.6 to generate image captions for tweet images (with tweet metadata).
   ![CleanShot 2024-03-07 at 23 31 26@2x](https://github.com/jerlinn/X-Insight/assets/91647085/6a80c97f-614b-4fce-b6e2-4e6c33cd5152)


## Sample Output

The project includes sample output files for reference:

- `sample_output_json.json`: A sample JSON file containing the fetched Twitter data.
- `sample_exported_excel.xlsx`: A sample Excel file exported from the JSON data.

Feel free to explore and modify the code to suit your specific data analysis requirements.



## FAQs:

- Will I get banned? Could this affect my account?

  - Selenium is one of the safest scraping methods out there, but it's still best to be cautious when using it for personal projects.
  - I've been using it for quite a while without any issues.
  - (Though, if you've got a spare / alt account, I'd recommend using that one's auth token instead)
- How do I find the auth token?

  - Check out this for a step-by-step guide!
    - [video demo](https://www.youtube.com/watch?v=MhKMNsbjug4)

## Credits

- [AlexZhangji](https://github.com/AlexZhangji/Twitter-Insight-LLM)
- [𝕏 @GZhan5](https://twitter.com/GZhan5)

## Acknowledgements

- Initial structure and parts of the Selenium code inspired by [Twitter-Scrapper](https://github.com/Mostafa-Ehab/Twitter-Scrapper).
- The image captioning feature is powered by the OpenAI API. You should be able to achieve similar results using Gemini 1.0.

For any questions or issues, please open an issue in the repository.

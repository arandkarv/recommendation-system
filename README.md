The project uses kaggle datasets 
datset link : https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset
It is suggested to comput the embeddings using gpu accelerator and svae it in local directory then compute the cosine similarity
the output is of two types if the movie is present in database we used hybrid engine S-BERT followed by SVD if the movie is not present we simply used S-BERT by taking overview we just recommended the top 10 movies 
output 1: If user entered movie is present in database ![Screenshot 2024-05-06 203806](https://github.com/arandkarv/recommendation-system/assets/115916938/c3ccb64f-e79b-437b-8c5a-18805423be54)
output 2: If not present ![Screenshot 2024-05-06 203943](https://github.com/arandkarv/recommendation-system/assets/115916938/b43cb7a2-3367-4bad-bb1b-52a58a69ea9b)
The kaggle version does'nt supports the gradio so opeen in colab code it up for gradio interface
to work with grado interfaces exectue the try and except in the function given below


def get_movie_list(user_id, movie_title):
    # place the try except block code here
    return "hello"

# Create Gradio interface
with gr.Blocks() as demo:
    user_id = gr.Textbox(label="Enter a user ID", placeholder="7")
    movie_title = gr.Textbox(label="Enter a movie title", placeholder="Toy Story 2")
    submit = gr.Button("Submit")

    with gr.Row():
        movie_list_output = gr.Dataframe(label="Movie List")
        rating_output = gr.Dataframe(label="Predicted User Rating")

    submit.click(get_movie_list, [user_id, movie_title], [movie_list_output, rating_output])

demo.launch()

# Gemini-QA-Chat Bot-
QA Chat Bot Using Google Gemini 
Hi Folks, have a build a QA Chat Bot using Google Gemini and streamlit. 
Code for the same in below lines 
#importing important libraries which we will be using for this project. 
import streamlit as st 
import os 
import google.generativeai as genai




#configuring Google Gemini API KEY
genai.configure(api_key="Your API KEY")
model=genai.GenerativeModel("gemini-pro")

#QA Chat Bot 
def get_gemini_response(question):
    
    response=model.generate_content(question)
    return response.text
#Streamlit App Title
st.set_page_config(page_title="Q&A Demo")
st.header("Gemini LLM Application")
input=st.text_input("Input: ",key="input")
submit=st.button("Ask the question")
if submit:
    response=get_gemini_response(input)
    st.subheader("The Response is")
    st.write(response)

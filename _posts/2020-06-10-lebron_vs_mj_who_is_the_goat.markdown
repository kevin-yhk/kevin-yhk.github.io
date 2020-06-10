---
layout: post
title:      "Lebron vs MJ, who is the GOAT"
date:       2020-06-10 05:47:50 +0000
permalink:  lebron_vs_mj_who_is_the_goat
---


The project is structured in a way such that I can run both front-end and the back-end at the same time. The back-end is comprised of the Rails sever running on localhost:3000 while the front-end Javascript and HTML/CSS run separately on the browser of your choice. This separation also allows both ends to be utilized together or separately.

A rails generator for resource was used to quickly make the two models, players and comments. Once created, the controllers are populated with index show and destroy to provide proper routing to the RESTful conventions that will be used in this project. 
```
class CommentsController < ApplicationController
    def index
        @comments = Comment.all
        render json: @comments 
    end

    def show
        find_comment
        render json: @comment
    end

    def destroy
        comment = Comment.find_by(id: params[:id])
        comment.destroy
        render json: comment
    end

end
```

When fetching our data from the back-end, the DOMContentLoaded event is performed when the HTML document has been fully fulled so that we can fetch the list of players and comments and render in the information that we need.
```
function displayUpdatedComment(){
    fetch("http://localhost:3000/comments", {
        method: 'GET',
        
})
.then(resp => resp.json())
.then(comment => {
    console.log(comment)
    let li = ``; 
        comment.forEach(comment => { 
            li += `<tr> 
                <td>Name: ${comment.name} </td><br>
                <td>Comment: ${comment.content}</td><br>  
                <button type="button" onclick="deleteComment(${comment.id})">Delete</button><br>         
            </tr><br>`; 
            
        }); 
        
    document.getElementById("content").innerHTML = li; 
    
})

}
```

Added features such as event listeners help us perform specific actions on the web page such as a simple click of a button or simply loading up the page from the start.
```
document.addEventListener("DOMContentLoaded", hide)

document.getElementById("whatever").addEventListener("click", showInfo)


function showInfo(){
    getplayer()
    document.getElementById("whatever").style.display="none"
    document.getElementById("content").style.display="block"
    document.getElementById("king").style.display="block"
    document.getElementById("air").style.display="block"
}


function hide(){
    displayNewComment()
    document.getElementById("content").style.display="none"
    document.getElementById("king").style.display="none"
    document.getElementById("air").style.display="none"

}
```
This was undoubtely a fun project with lots of stretch goal additions that can be added on to this project. Although I am excited to finally utilize some frameworks, I believe that learning about vanilla JavaScript was very important to steer me towards a better understanding of future frameworks and how they can help make things super streamlined. 

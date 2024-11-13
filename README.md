<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        paragraph{
            padding-left: 20px;
            padding-right: 20px;
            margin-left: 18px;
            margin-left: 18px;
        }
        button{
            margin-left: 200px;
        }
        #content{
            width: 40%;
           
          
     
        }
    </style>
</head>
<body>
    <div id="container">
        <input type="text" name="" id="item">
        <button id="add" style="margin: 0;">Add</button>
        <div id="content"></div>
    </div>
<script>
    let item=document.getElementById("item");
    let add=document.getElementById("add");
    let content=document.getElementById("content");
    
    add.addEventListener("click",()=>{
        if(item.value.trim()===""){
            alert("User must have one to-do-task");
        return false;
    }
    else{
    add.addEventListener("click",()=>{
        let paragraph=document.createElement("p");
        paragraph.textContent=item.value;
        item.value="";
        content.appendChild(paragraph);
        let deletee=document.createElement("button");
        deletee.textContent="Delete";
       
    
        paragraph.appendChild(deletee);
        paragraph.addEventListener("click",()=>{
            if(paragraph.style.textDecoration==="line-through"){
                paragraph.style.textDecoration="none";
            }
            else{
                paragraph.style.textDecoration="line-through";
            }
        });
        deletee.addEventListener("click",()=>{
            event.stopPropagation();
            deletee.style.textDecoration="none";
            content.removeChild(paragraph);
        });
    });
    item.addEventListener("keydown",(event)=>{
        if(event.key==="Enter"){
            add.click();
        }
    });
    
        return true;
    }
});
    </script>
</body>
</html>

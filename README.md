<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Cats</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="container">
        <div class="cat">
            <img src="ds2.png" id="img">
        </div>

        <div class="btn">
            <button>Genrate Random Cat Images</button>
        </div>
    </div>

    <script>
        
        let url = "https://cataas.com/cat";
        let btn = document.querySelector("button");
        let img=document.getElementById("img");
        btn.addEventListener("click", async () => {
            let imgLink="";
            console.log("button is clicked");
            imgLink = await genrateImages();
          
            img.setAttribute("src", imgLink.url);

        })

        async function genrateImages() {
            try {

                let data = await fetch(url);
                
                return data;

            } catch (err) {
                return err;
            }
        }

    </script>
</body>

</html>

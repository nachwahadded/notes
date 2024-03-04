 `function loadVidelistFromJson(){
        `var xhr = new XMLHttpRequest();
        `xhr.onreadystatechange = function () {
          ``  if (xhr.readyState === XMLHttpRequest.DONE) {
            ``    if (xhr.status === 200) {
              ``      var data = JSON.parse(xhr.responseText);
                ``    console.log("JSON data:", JSON.stringify(data, null, 2));

                    populatePlaylist(data);
                } else {
                    console.error("Failed to load JSON file:", xhr.statusText);
                }
            }
        }
        xhr.open("GET", "listemovie.json", true);
        xhr.send();
    }

    function populatePlaylist(data) {
           movielistModel = data;
           // Trigger GridView population after setting movielistModel
           gridView.model.clear();
           for (var i = 0; i < movielistModel.length; ++i) {
               gridView.model.append({ "name": movielistModel[i].name, "URL": movielistModel[i].URL, "imageSource": movielistModel[i].imageSource });
           }
       }
       
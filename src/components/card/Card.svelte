<script>
    let rating = 0;
    let name = "";
    let description = "";
  
    function setRating(value) {
      rating = value;
    }
  
    function submitRating() {
  const Ratings = document.getElementById("Ratings");
  const Rating = document.createElement("h1");
  const Name = document.createElement("h1")
  const Description = document.createElement("h1");
  const BR = document.createElement("br");
  Rating.innerText = rating.toString();
  Name.innerText = name;
  Description.innerText = description;
  Name.classList.add('NameAdd');           // Use classList.add to add classes
  Description.classList.add('DescriptionAdd');
  Rating.classList.add('RatingAdd');
  Ratings.innerHTML = "";
  Ratings.append(Name, Description, Rating);
}

  </script>
  
  <style>
    .star-rating,
    .Rating {
      display: flex;
      justify-content: center;
    }
  
    .star {
      font-size: 7vh;
      cursor: pointer;
      color: gray;
    }
  
    .selected {
      color: #fff135;
    }
  
    .Name,
    .Description {
      width: 30vh;
      height: 3vh;
      border: 0;
      border-radius: 3vh;
    }
  
    .NameName,
    .DescriptionName {
      font-size: 3vh;
    }
  
    .Name,
    .Description,
    .NameName,
    .DescriptionName {
      margin-left: 1vh;
    }
  
    .SubmitButton {
      display: flex;
      justify-content: center;
      background-color: white;
      width: 30vh;
      height: 5vh;
      border: 0;
      border-radius: 3vh;
      margin: 0 auto;
      font-size: 3vh;
    }
  
    input:focus {
      outline: none;
    }
  
    .SubmitButton:hover {
      background-color: #d1d2d3;
    }

    .NameAdd {
        font-size: 7vh;
    }

    .DescriptionAdd {
        font-size: 5vh;
    }

    .RatingAdd {
        font-size: 3vh;
    }

    .NameAdd, .DescriptionAdd, .RatingAdd {
        text-align: center;
    }

    .Ratings {
        display: flex;
        justify-content: center;
        gap: 1vh;
    }
  </style>
  
  <div class="Rating">
    <label class="NameName" for="">Name:</label>
    <input aria-required="true" type="text" bind:value={name} class="Name">
    <label class="DescriptionName" for="">Descrição:</label>
    <input aria-required="true" type="text" bind:value={description} class="Description">
  </div>
  <div class="star-rating">
    {#each [1, 2, 3, 4, 5] as starRating}
      <span class="star {rating >= starRating ? 'selected' : ''}" on:click={() => setRating(starRating)}>★</span>
    {/each}
  </div>
  <button on:click={submitRating} class="SubmitButton">Enviar</button>
  <div class="Ratings" id="Ratings"></div>
  
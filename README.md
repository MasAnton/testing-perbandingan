  $(".modal-detail-button").on("click", function () {
      $.ajax({
        url: "http://www.omdbapi.com/?apikey=dca61bcc&i=" + $(this).data("imdbid"),
        success: (m) => {
          const movieDetail = `<div class="container-fluid">
                                  <div class="row">
                                    <div class="col-md-3">
                                      <img src="${m.Poster}" class="img-fluid" alt="" />
                                    </div>
                                    <div class="col-md">
                                      <ul class="list-group">
                                        <li class="list-group-item">
                                          <h4>${m.Title}</h4>
                                        </li>
                                        <li class="list-group-item"><strong>${m.Genre}</strong></li>
                                        <li class="list-group-item"><strong>${m.Director}</strong></li>
                                        <li class="list-group-item"><strong>${m.Actors}</strong></li>
                                        <li class="list-group-item"><strong>${m.Runtime}</strong> <br />${m.Plot}</li>
                                      </ul>
                                    </div>
                                  </div>
                                </div>`;
          $(".modal-body").html(movieDetail);
        },
      });
    });

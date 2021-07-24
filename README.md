<?php
  include('header.php');
?>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>FOOD ORDER</title>
  <!-- Font Awesome -->
  <link rel="icon" href="images/logo.png" type="image/x-icon" />
<link
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css"
  rel="stylesheet"
/>
<!-- Google Fonts -->
<link
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,700&display=swap"
  rel="stylesheet"
/>
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap"
  />
<!-- MDB -->
<link
  href="https://cdnjs.cloudflare.com/ajax/libs/mdb-ui-kit/3.6.0/mdb.min.css"
  rel="stylesheet"
/>
<link rel="stylesheet" href="index.css">
<style>
  .tab{

    display: flex;
    justify-content: center;
    background: crimson !important;
    border-color: crimson !important;
  }
  
  .nav-tabs .nav-item.show .nav-link, .nav-tabs .nav-link.active {
    color:antiquewhite !important;
    background: crimson !important;
    border-color: crimson !important;
    /* border-bottom: black !important; */
}
.link1:hover{
  background: crimson !important ;
  border-color:crimson !important ;
}
</style>
</head>
<body>

<!-- carousel -->
<div id="carouselExampleCaptions" class="carousel slide" data-mdb-ride="carousel">
      <div class="carousel-indicators">
        <button
          type="button"
          data-mdb-target="#carouselExampleCaptions"
          data-mdb-slide-to="0"
          class="active"
          aria-current="true"
          aria-label="Slide 1"
        ></button>
        <button
          type="button"
          data-mdb-target="#carouselExampleCaptions"
          data-mdb-slide-to="1"
          aria-label="Slide 2"
        ></button>
        <button
          type="button"
          data-mdb-target="#carouselExampleCaptions"
          data-mdb-slide-to="2"
          aria-label="Slide 3"
        ></button>
      </div>
      <div class="carousel-inner">
        <div class="carousel-item active">
          <img
            src="img/1080-x-400px-Grill-Veggies-on-Table-feature.jpg"
            class="d-block w-100"
            alt="..."
            style="height: 500px;"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>First slide label</h5>
            <p>Nulla vitae elit libero, a pharetra augue mollis interdum.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="img/banner_ottawa_chicken_burger.jpg"
            class="d-block w-100"
            alt="..."
            style="height: 500px;"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Second slide label</h5>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
          </div>
        </div>
        <div class="carousel-item">
          <img
            src="img/R1f8b942c0e18a642f6e47e35e415ae9b.jfif"
            class="d-block w-100"
            alt="..."
            style="height: 500px;"
          />
          <div class="carousel-caption d-none d-md-block">
            <h5>Third slide label</h5>
            <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur.</p>
          </div>
        </div>
      </div>
      <button
        class="carousel-control-prev"
        type="button"
        data-mdb-target="#carouselExampleCaptions"
        data-mdb-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
  
      <button
        class="carousel-control-next"
        type="button"
        data-mdb-target="#carouselExampleCaptions"
        data-mdb-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
</div>
  <div class="">
    <ul class="nav nav-tabs mb-3 tab" id="myTab0" role="tablist">
      <li class="nav-item" role="presentation">
        <button
          class="nav-link active link1"
          id="home-tab0"
          data-mdb-toggle="tab"
          data-mdb-target="#home0"
          type="button"
          role="tab"
          aria-controls="home"
          aria-selected="true"
          >
          All-menus
        </button>
      </li>
      <li class="nav-item" role="presentation">
        <button
          class="nav-link link1"
          id="profile-tab0"
          data-mdb-toggle="tab"
          data-mdb-target="#profile0"
          type="button"
          role="tab"
          aria-controls="profile"
          aria-selected="false"
          >
          non-vegs-menu
        </button>
      </li>
      <li class="nav-item" role="presentation">
        <button
          class="nav-link link1"
          id="contact-tab0"
          data-mdb-toggle="tab"
          data-mdb-target="#contact0"
          type="button"
          role="tab"
          aria-controls="contact"
          aria-selected="false"
          >
          vegs-menu
        </button>
      </li>
    </ul>
  </div>  
<div class="tab-content" id="myTabContent0" style="margin:25px;">
<div
		class="tab-pane fade show active d-flex"
		id="home0"
		role="tabpanel"
		aria-labelledby="home-tab0">

		<div class="container">
      <div id="message"></div>
			<div class="row mt-2 pb-3">
				<?php 
					include('config.php');
	 				$sql = mysqli_query($conn,"SELECT * FROM products");
					while($row = mysqli_fetch_assoc($sql)){
				?>
					<div class="col-md-3">
						<div class="card text-center" style="width: 250px;border-radius: 10px;box-shadow:4px 4px black ; background: linear-gradient(to bottom, #ffffff 0%, #99ccff 100%);">
							  <img src="<?php echo $row['product_image'];?>" class="card-img-top" style="height:150px !important; border-radius:12px;"/>
                <div class="card-body" style="height:120px; background: linear-gradient(to bottom, #ffffff 0%, #99ccff 100%);">
									<h6 class="card-title" style="margin-top:-15px;margin-left:12px;">
                  <?php echo $row['product_name'];?></h6>
									<p class="card-text"style="margin-top: 0;
										margin-bottom: 2px;
									"> &#8377 <?php echo $row['product_price'];?></p>
									<p class="card-text" style="margin: -5px;
									"><?php echo $row['disc_price'];?>% OFF &#8377 <?php echo $row['product_price'];?></p>
                </div>  
                <div class="card-footer p-1">
                  <form action="" class="form-submit">
                    <input type="hidden" class="pid" value="<?= $row['id'] ?>">
                    <input type="hidden" class="pname" value="<?= $row['product_name'] ?>">
                    <input type="hidden" class="pprice" value="<?= $row['product_price'] ?>">
                    <input type="hidden" class="pimage" value="<?= $row['product_image'] ?>">
                    <input type="hidden" class="pcode" value="<?= $row['pcode'] ?>">
                    <?php
                    if(isset($_SESSION['usremail'])){?>
                      <button class="btn btn-info btn-block addItemBtn" >Add to cart</button>
                    <?php } else{?>
                      <a href="login.php" class="btn btn-info btn-block">Add to cart</a>
                    <?php } ?>
                    
                  </form>
                </div>    
						</div>
					</div>
				<?php } ?>
			</div>
		</div>
	</div>
    <div class="tab-pane fade" id="profile0" role="tabpanel" aria-labelledby="profile-tab0">
    <div class="tab-pane fade" id="contact0" role="tabpanel" aria-labelledby="contact-tab0">
      Tab 3 content
    </div>
</div>


<!-- end your project -->
<script
type="text/javascript"
src="https://cdnjs.cloudflare.com/ajax/libs/mdb-ui-kit/3.3.0/mdb.min.js">
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js'></script>

<script type="text/javascript">
  $(document).ready(function(){
    $(".addItemBtn").click(function(e){
      e.preventDefault();
      var $form = $(this).closest(".form-submit");
      var pid = $form.find(".pid").val();
      var pname = $form.find(".pname").val();
      var pprice = $form.find(".pprice").val();
      var pimage = $form.find(".pimage").val();
      var pcode = $form.find(".pcode").val();
      var email = "<?php echo $_SESSION['usremail']; ?>";
      $.ajax({
        url: 'action.php',
        method: 'post',
        data: {
          pid: pid,pname: pname,pprice: pprice,pimage: pimage,pcode: pcode, email:email
        },
        success: function(response){
          $("#message").html(response);
          load_cart_item_number();
        }
      });
    });

    // Load total no.of items added in the cart and display in the navbar
    load_cart_item_number();

    function load_cart_item_number() {
      $.ajax({
        url: 'action.php',
        method: 'get',
        data: {
          cartItem: "cart_item"
        },
        success: function(response) {
          $("#cart-item").html(response);
        }
      });
    }
  });
  </script>

</body>

<?php
  include 'contact.php';
?>
</html>
<?php include 'footer.php';?>

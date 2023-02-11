<script>
    import simpleParallax from 'simple-parallax-js';
    import Carousel from "svelte-flickity";
    import { onMount } from 'svelte';

	/**
	 * @type {any}
	 */
	let y

    onMount(() => {
        let image = document.getElementsByClassName('thumbnail');
        new simpleParallax(image);
        let desc_1 = document.getElementsByClassName('desc_1');
        new simpleParallax(desc_1);
        let desc_2 = document.getElementsByClassName('desc_2');
        new simpleParallax(desc_2);

    });

    let classY = "default-navbar"
	$: callfunc = checkY();
	function checkY() {
        if (y > 50) { 
            classY = "scroll-navbar"
        }
    
	}

    const carouselOptions = {
        autoPlay: false,
		freeScroll: false,
		freeScrollFriction: 0.03,
		wrapAround: true
	};
    let video_landing = "video_landing.mp4"
    // let video_landing = "INTRAORDINAIRE_final.mp4"
</script>

<svelte:window bind:scrollY={y} />
<div class="wrapper">

<section class="showcase p-0">
    <div class="video-container">
        <video src="{video_landing}" autoplay muted loop></video>
    </div>
    <div class="content w-100 h-100">
        {#if y < 100}
        <nav class="navbar navbar-expand-lg m-0 p-4 fixed-top"> 
            <div class="container-fluid px-4">
              <a class="navbar-brand" href="#">LOGO</a>
            
            <div>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
                <div class="navbar-nav">
                  <a class="nav-link p-3" aria-current="page" href="#">Projets</a>
                  <a class="nav-link p-3" href="#">Equipe</a>
                  <a class="nav-link p-3" href="#">Contacts</a>
                </div>
            </div>
        </div>
        </nav>
        {:else}
        <nav class="navbar navbar-expand-lg m-0 p-4 fixed-top scrolled"> 
            <div class="container-fluid px-4">
              <a class="navbar-brand" href="#">LOGO</a>
            
            <div>
              <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
              </button>
                <div class="navbar-nav">
                  <a class="nav-link p-3" aria-current="page" href="#">Projets</a>
                  <a class="nav-link p-3" href="#">Equipe</a>
                  <a class="nav-link p-3" href="#">Contacts</a>
                </div>
            </div>
        </div>
        </nav>
        {/if}

        <div class="h-100 d-flex justify-content-center align-items-center">
            <div>
                <!-- <img class="thumbnail" src="logo.png" alt="logo" width=50> -->
                <!-- <h1>REC-OUT Logo</h1> -->
                <img src="logo.png" width=250 alt="Fb">
                <h3>REC-OUT</h3>
            </div>
        </div>
    </div>
</section>

<section class="description container-full mx-auto text-left p-5">
    <div class="container mx-auto mt-5">
        <div class="row mb-4">
            <div class="col-1"></div>
            <div class="col-4 d-flex flex-row align-items-center justify-content-center">
                <div>
                    <h2 class="title mb-3">Rec-Out
                    <h3 class="mb-4">Ce que nous sommes</h3>

                    </h2>
                    
                    <p class="mt-4 desc-p">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                    </p>
                </div>
            </div>
            <div class="col-1"></div>
            <div class="col-5 imgs mb-5">
                <img class="desc_1 w-100" src="img/description/1.jpg" alt="set">
                <img class="desc_2 w-50" src="img/description/2.jpg" alt="set">
            </div>
        </div>
    </div>
</section>

<section class="projects container-full py-5">
<Carousel options={carouselOptions}>
	<div class="carousel-cell c1 me-5 mb-3">
        <div class="w-100 h-100 d-flex flex-row text-center justify-content-center align-items-center">
            <div>
                <h2 class="mb-5 h1">Titre du projet 1</h2>
                <a class="link-project p-3" href="">En savoir plus</a>
            </div>
        </div>
    </div>
	<div class="carousel-cell c2 me-5 mb-3">
        <div class="w-100 h-100 d-flex flex-row text-center justify-content-center align-items-center">
            <div>
                <h2 class="mb-5 h1">Titre du projet 2</h2>
                <a class="link-project p-3" href="">En savoir plus</a>
            </div>
        </div>
    </div>
	<div class="carousel-cell c3 me-5 mb-3">
        <div class="w-100 h-100 d-flex flex-row text-center justify-content-center align-items-center">
            <div>
                <h2 class="mb-5 h1">Titre du projet 3</h2>
                <a class="link-project p-3" href="">En savoir plus</a>
            </div>
        </div>
    </div>
</Carousel>
</section>



<section class="description-2 container-fluid mx-auto text-center p-5">
    <div class="row mb-4">
        <div class="col-6 mx-auto">
            <h2 class="title mb-3">Mais que serait Rec-Out sans son équipe ?</h2>
            <p class="mt-4 desc-p">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
        </div>
    </div>
</section>

<section class="team container-fluid mx-auto">
    <!-- <h2 class="title text-uppercase p-5">Notre équipe</h2> -->
    <div class="cardboard row">
        <div class="card-people p1 col-3">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p2 col-3">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>
        <div class="card-people p1 col-3">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p2 col-3">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>
    </div>

    <div class="cardboard row">
        <div class="card-people p1 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p2 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p3 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p1 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p2 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>

        <div class="card-people p3 col-2">
            <a class="w-100 h-100 d-flex" href="">
                <div class="poste mt-auto w-100 p-3">
                    <h3 class="h5">NAME NAME</h3>
                    <h4 class="h6">Nom du poste</h4>
                </div>
            </a>
        </div>
    </div>
        

</section>


<section class="contact container-fluid mx-auto text-center mt-5 p-5">
    <div class="row mb-4">
        <div class="col-6 mx-auto">
            <h2 class="title mb-3">Contactez-nous !
            </h2>
            <p class="mt-4 desc-p">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </p>
            <br />
            <p>Par email à : <strong>email@gmail.com</strong>
            </p>
        </div>
    </div>

    <div class="text-center social-icons mb-5 pt-4">
        <a href="" class="mx-4">
            <img src="icons/fb-2.svg" width=50 alt="Fb">
        </a>
        <a href="" class="mx-4">
            <img src="icons/mess-2.svg" width=50 alt="Fb">
        </a>
        <a href="" class="mx-4">
            <img src="icons/lin-2.svg" width=50 alt="Fb">
        </a>
    </div>
</section>

<!-- Remove the container if you want to extend the Footer to full width. -->
<div class="container-fluid footer">
    <!-- Footer -->
    <footer class="text-center">
      <!-- Grid container -->
      <div class="container-fluid">
        <section class="mb-5 pt-5">
          <div class="row d-flex justify-content-center">
            <div class="col-lg-8">
              <p class="m-0 p-0">
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
                Ici un petit texte si l'on souhaite.
              </p>
            </div>
          </div>
        </section>
        <!-- Section: Text -->
        <!-- Section: Social -->
      </div>
      <!-- Grid container -->
  
      <!-- Copyright -->
      <div
           class="text-center p-3 small copyright"
           >
        © 2023 Rec-out.fr
      </div>
      <!-- Copyright -->
    </footer>
    <!-- Footer -->
  </div>
  <!-- End of .container -->
  
</div>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lora&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;0,700;1,300&display=swap');
$enable-negative-margins: true;

:root {
	--primary-color: #3a4052;
    --theme-1: rgb(0, 225, 255);
    --theme-2: rgb(255, 0, 204);
    --theme-1-o: rgb(0, 225, 255, 0.1);
    --theme-2-o: rgb(255, 0, 204, 0.1);
}

.navbar {
    // background: red;
    color: white;
    // background: rgba(0, 0, 0, 0.5);

    a {
        color: white;
        font-weight: 100;
        text-transform: uppercase;
        height: 100%;
        box-shadow: 0 0 0 rgba(0, 0, 0, 0);
        transition: all 0.2s ease-in-out;

        &:hover {
            background-color: var(--theme-2);
            color: white;
            box-shadow: 4px 4px 0 var(--theme-1);
        }
    }
}

.scrolled {
        transition: all 0.2s ease-in-out;
    background: white;
    
    a {
        color: rgb(49, 49, 49);
        font-weight: 100;
        text-transform: uppercase;
        height: 100%;
        box-shadow: 0 0 0 rgba(0, 0, 0, 0);
        transition: all 0.2s ease-in-out;

        &:hover {
            background-color: var(--theme-2);
            color: white;
            box-shadow: 4px 4px 0 var(--theme-1);
        }
    }
}

* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}

.wrapper {
	font-family: 'Open Sans', sans-serif;
	line-height: 1.5;
    font-family: 'Lato', sans-serif !important;
}

a {
	text-decoration: none;
	color: var(--primary-color);
}

h1 {
	font-weight: 300;
	font-size: 60px;
	line-height: 1.2;
	margin-bottom: 15px;
}

.showcase {
	height: 100vh;
	display: flex;
	align-items: center;
	justify-content: center;
	text-align: center;
	color: #fff;
}

.video-container {
	position: absolute;
    // box-shadow: 0 100px 100px white;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	overflow: hidden;
	background: var(--primary-color) url('./https://traversymedia.com/downloads/cover.jpg') no-repeat center
		center/cover;
}

.video-container video {
	min-width: 100%;
	min-height: 100%;
  position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	object-fit: cover;
}

.video-container:after {
	content: '';
	z-index: 1;
	height: 100%;
	width: 100%;
	top: 0;
	left: 0;
	background: rgba(0, 0, 0, 0.5);
	position: absolute;
}

.content {
	z-index: 2;
}


.footer {
    // background-color: var(--theme-2);
    // background: linear-gradient(45deg, var(--theme-1-o), rgba(35, 165, 213, 0.072), var(--theme-2-o));
    // background-size: 200% 100%;
    // animation: gradient 10s ease infinite;
    // border: 0px solid red;
    background-color: #fff8fe;
    // background-color: var(--theme-2-o);

    a {
        color: var(--theme-2);
    }
}
.copyright {
    background-color: rgb(255, 240, 254)    // background-color: var(--theme-2-o);
}

h2.title {
    font-family: 'Anton', sans-serif !important;
}

.description {
    background: linear-gradient(-45deg, var(--theme-1-o), rgba(35, 165, 213, 0.072), var(--theme-2-o));
    background-size: 400% 400%;
    animation: gradient 10s ease infinite;

    p {
        // font-family: 'Lora', serif;
    }
    
    .imgs {
        position: relative;
        top:0;
        left:0;
        z-index: 1;
        box-shadow: 10px 10px 0 var(--theme-1);

        .desc_1 {
            position: relative;
            top:0;
            left:0;
        }
        .desc_2 {
            position: absolute;
            // top:50px;
            left:-40px;
            bottom: 0;
            box-shadow: 10px 10px 0 var(--theme-2);
        }
    }
}

@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }

    50% {
    background-position: 100% 50%;
    }

    100% {
        background-position: 0% 50%;
    }
}

.projects {
    box-shadow: 0 -100px 100px white;
    // border: 2px solid red;
    .carousel-cell {
        h2 {
            color: white;
            text-transform: uppercase;
            font-family: 'Anton', sans-serif !important;
        }
        width: 66%;
        height: 700px;
        counter-increment: gallery-cell;

        

        .link-project {
            color: white;
            // font-size: 1.5rem;
            text-transform: uppercase;
            // background: var(--theme-2);  
            background: var(--theme-2);  
            transition: all 0.2s ease-in-out;

            &:hover {
                color: white;
                background: var(--theme-2);  
                box-shadow: 5px 5px 0 var(--theme-1);
            }
        }
    }

    // /* cell number */
    // .carousel-cell:before {
    // display: block;
    // text-align: center;
    // content: counter(gallery-cell);
    // line-height: 200px;
    // font-size: 80px;
    // color: white;
    // }

    .c1 {
        background: url("img/projects/1.jpg")  no-repeat center center/cover;
    }
    .c2 {
        background: url("img/projects/2.jpg")  no-repeat center center/cover;
    }
    .c3 {
        background: url("img/projects/3.jpg")  no-repeat center center/cover;
    }
}

.team {
    h2 {
        // background: linear-gradient(45deg, var(--theme-1-o), rgba(35, 165, 213, 0.072), var(--theme-2-o));
        // background-size: 200% 100%;
        // animation: gradient 10s ease infinite;
    }

    p {
        font-family: 'Lora', serif;
    }

    .card-people {
        overflow: hidden;
        height: 400px;
        a {
            .poste {
                transition: all 0.2s ease-in-out;
                opacity: 1;
                margin-bottom: -10px;
                background: rgba(0, 0, 0, 0.5);

                h3 { color: white; }
            }

            &:hover, &:focus, &:active {
                .poste {
                background: var(--theme-1);
                    margin-bottom: 0;
                    opacity: 1;
                }
                h3 { color: var(--theme-2); }
            }
        }
        .poste {
            color: var(--theme-2);
            align-self: end;

            h3 {
                text-transform: uppercase;
                font-weight: normal;
                // font-family: 'Anton', serif;
            }

            h4 {
                color: white;
                margin-bottom: 10px;
        // font-family: 'Lora', serif;
            }
        }

    }

    .p1 {
            background: url("img/team/1.jpg")  no-repeat center center/cover;
        }
    .p2 {
            background: url("img/team/2.jpg")  no-repeat center center/cover;
        }
    .p3 {
            background: url("img/team/3.jpg")  no-repeat center center/cover;
        }
}


</style>
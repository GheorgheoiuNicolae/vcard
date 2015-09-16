<div class="header">
  <h2 class="logo_animated logo_animated--open"  style="top: 80%">
	<b class="animated_fn"><i>FE</i></b>
	<span class="animated__slash">/</span>
	<b class="animated_ln"><i>UX</i></b>
	<b class="animated_profession">Developer</b>
  </h2>
</div>




<script>
	$(".header").on({
	  "click.header": function() {
		$(".logo_animated").toggleClass("logo_animated--open");
	  }
	});
	
	setTimeout( function() {
	  $(".logo_animated").addClass("logo_animated--slow").removeClass("logo_animated--open");
	},1000);

	setTimeout( function() {
	  $(".logo_animated").removeClass("logo_animated--slow");
	},2400);
</script>





.logo {
  user-select: none;
  cursor: default;
  height: 100%;
  &_animated {
    font-family: Lato, Arial, sans-serif;
    text-shadow: 0 1px 1px rgba(42,43,61,0.5);
    font-size: 86px;
    height: $headerHeight;
    line-height: $headerHeight;
    font-weight: 300;
    position: absolute;
    top: 50%;
    left: 120px;
    margin: -($headerHeight/2) 0 0;
    transition: all 0.6s ease-out;
    transition-delay: 0.5s;
    z-index: 2;
	  
    @media screen and ( max-width: 1000px ) {
      transform: scale(0.9);
    }
    @media screen and ( max-width: 850px ) {
      transform: scale(0.65);
    }
    @media screen and ( max-width: 700px ) {
      transform: scale(0.5);
    }
  }
}

.animated {
  &__slash {
    color: $red;
    font-weight: 300;
    position: absolute;
    top: -$gap/2;
    left: $headerHeight - $gap*2;
    margin-left: $gap/2;
    transform: scale(1.6);
    z-index: 5;
  }

  &_fn, &_ln {
    top: 50%;
    margin-top: -$headerHeight;
    position: absolute;
    width: $headerHeight*2;
    height: $headerHeight*2;
    overflow: hidden;
    transform: rotateZ($angle);
    i {
      font-style: normal;
      top: 0;
      left: 0;
      position: absolute;
      width: $headerHeight*2;
      height: $headerHeight*2;
      line-height: $headerHeight*2;
      transform: rotateZ(-$angle);
    }
  }

  &_fn {
    text-align: right; 
    direction: rtl;
    margin-left: -$headerHeight - $gap + 1px;
    i {
      text-indent: -$clip;
    }
  }

  &_ln {
    margin-left: $headerHeight + $gap;
    i { 
      text-indent: -$clip;
    }
  }

  &_profession {
    font-weight: 300;
    position: absolute;
    top: 0;
    left: $headerHeight*2.5;
  }
  &_fn, &_ln, &_fn i, &_ln i, &_profession, &__slash {
    transition: all 0.6s cubic-bezier(0.555, -0.375, 0.000, 1.615);
  }
}

.logo_animated--open {
  .animated {
    &_fn, &_ln {
      i {
        text-indent: $clip;
      }
    }
    &_profession {
      transform: translateX( $clip*2 );
      opacity: 0.2;
    }
    &__slash {
      transform: scale(1.6) rotateZ( -$angle );
    } 
  }
}

.logo_animated--slow {
  .animated {
    &_fn, &_ln, &_fn i, &_ln i, &_profession, &__slash {
      transition: all 1.2s cubic-bezier(0.555, -0.375, 0.000, 1.615);
    } 
  }
}

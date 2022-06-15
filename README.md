# gridinfo

<!-- load more and less jquery code -->
$(document).ready(function () {
  $('.trackrecord-section .casestudy-box:lt(6)').show();
  $('#show-caseLess').hide();
  var items =  $(".casestudy-box").length;
  var shown =  6;
  $('#load-caseMore').click(function () {
      $('#show-caseLess').css("display", "inline-block");
      shown = $('.trackrecord-section .casestudy-box:visible').length+6;
      if(shown< items) {
        $('.trackrecord-section .casestudy-box:lt('+shown+')').show(300);
      } else {
        $('.trackrecord-section .casestudy-box:lt('+items+')').show(300);
        $('#load-caseMore').hide();
      }
  });
  $('#show-caseLess').click(function () {
      $('.trackrecord-section .casestudy-box').not(':lt(6)').hide(300);
      $('#load-caseMore').show();
      $('#show-caseLess').hide();
  });
});


<!-- header smoth fixed jquery code -->
var scroll_pos = 0;
$(document).scroll(function() { 
  scroll_pos = $(this).scrollTop();
      // var mq = window.matchMedia( "(min-width: 769px)" );
      if($(window).width() > 769){

        if(scroll_pos > 50) {
          $("#header").css({'padding': '0px 110px', 'transition': 'all .7s'});
          $("#header .btn-main").css({'padding': '10px 24px', 'transition': 'all .7s'});
          $("#header .navbar-brand img").css({'width': '90%', 'transition': 'all .7s'});
        }

        else{
          $("#header").css({'padding': '4px 110px'});   
          $("#header .btn-main").css({'padding': '13px 24px'});               
          $("#header .navbar-brand img").css({'width': '100%'});                   
        } 
      }
      
    });
    
<!--   smooth scroll on click jquery code -->
$("a[href='#opening-detail']").click(function() {
  $('html, body').animate({
    scrollTop: $("#opening-detail").offset().top
  }, 500);
  return false;
});


<!-- equal div height jquery code -->

$(document).ready(function(){
	var height = [];

	$('divclass').each(function(){
		height.push($(this).height());
	});

	var maxheight = Math.max.apply(null,height);

	$('divclass').height(maxheight);

});

/*
iqonic-Modern Business Startup Multipurpose Wordpress Theme
Author: iqonicthemes.in
Version: 1.0
Design and Developed by: iqonicthemes.in
*/

/*----------------------------------------------
Index Of Script
------------------------------------------------

1.Page Loader
2.Isotope
3.Masonry
4.Progress Bar
5.Counter
6.Tab Features
7.Back To Top
8.Accordion
9.Header
10.Magnific Popup
11.Owl Carousel
12.Wow Animation
13.tilt js
14.smooth-scrollbar

------------------------------------------------
Index Of Script
----------------------------------------------*/
var $ = window.jQuery =jQuery.noConflict();

(function(jQuery) {

    "use strict";
    jQuery(document).ready(function() {


        jQuery(window).on('load', function(e) {

	
	

            /*------------------------
            Page Loader
            --------------------------*/
            jQuery("#load").fadeOut();
            jQuery("#loading").delay(0).fadeOut("slow");

            jQuery('.kkkk').attr('onmousemove', 'color_hover(event)');
            // jQuery('.white-box').attr('data-top', 'transform:translatey(0)');

            if (jQuery("#scene").length) {
                var scene = document.getElementById('scene');
                var parallaxInstance = new Parallax(scene);
            }
            if (jQuery("#sceneq").length) {
                var sceneq = document.getElementById('sceneq');
                var parallaxInstance = new Parallax(sceneq);
            }
            if (jQuery("#sceneqq").length) {
                var sceneqq = document.getElementById('sceneqq');
                var parallaxInstance = new Parallax(sceneqq);
            }
            if (jQuery("#sceneqw").length) {
                var sceneqw = document.getElementById('sceneqw');
                var parallaxInstance = new Parallax(sceneqw);
            }
            if (jQuery("#sceneqe").length) {
                var sceneqe = document.getElementById('sceneqe');
                var parallaxInstance = new Parallax(sceneqe);
            }
            if (jQuery("#banner").length) {
                var banner = document.getElementById('banner');
                var parallaxInstance = new Parallax(banner);
            }
            if (jQuery("#bannertext").length) {
                var bannertext = document.getElementById('bannertext');
                var parallaxInstance = new Parallax(bannertext);
            }


            jQuery('.line-button').on('click', function(e) {
                var anchor = jQuery(this);
                jQuery('html, body').stop().animate({
                    scrollTop: jQuery(anchor.attr('href')).offset().top - 0
                }, 1500);
                e.preventDefault();
            });

            /*------------------------
            Isotope
            --------------------------*/
            jQuery('.isotope').isotope({
                itemSelector: '.iq-grid-item',
            });

            /*------------------------------
            filter items on button click
            -------------------------------*/
            jQuery('.isotope-filters').on('click', 'button', function() {
                var filterValue = jQuery(this).attr('data-filter');
                jQuery('.isotope').isotope({
                    resizable: true,
                    filter: filterValue
                });
                jQuery('.isotope-filters button').removeClass('active');
                jQuery(this).addClass('active');
            });
            var body = jQuery('body');
            jQuery('#menu-icon').bind('click', function() {
                body.toggleClass('menu-open');
                return false;
            });
            jQuery("#menu-icon").click(function() {
                jQuery(this).text(function(i, v) {
                    return v === 'Close' ? 'Menu' : 'Close'
                });
            });

            /*------------------------
            Masonry
            --------------------------*/
            var jQuerymsnry = jQuery('.iq-masonry-block .iq-masonry');
            if (jQuerymsnry) {
                var jQueryfilter = jQuery('.iq-masonry-block .isotope-filters');
                jQuerymsnry.isotope({
                    percentPosition: true,
                    resizable: true,
                    itemSelector: '.iq-masonry-block .iq-masonry-item',
                    masonry: {
                        gutterWidth: 0
                    }
                });
                // bind filter button click
                jQueryfilter.on('click', 'button', function() {
                    var filterValue = jQuery(this).attr('data-filter');
                    jQuerymsnry.isotope({
                        filter: filterValue
                    });
                });

                jQueryfilter.each(function(i, buttonGroup) {
                    var jQuerybuttonGroup = jQuery(buttonGroup);
                    jQuerybuttonGroup.on('click', 'button', function() {
                        jQuerybuttonGroup.find('.active').removeClass('active');
                        jQuery(this).addClass('active');
                    });
                });
            }

            /*------------------------
            Back To Top
            --------------------------*/
            jQuery('#back-to-top').fadeOut();
            jQuery(window).on("scroll", function() {
                if (jQuery(this).scrollTop() > 250) {
                    jQuery('#back-to-top').fadeIn(1400);
                } else {
                    jQuery('#back-to-top').fadeOut(400);
                }
            });

            // scroll body to 0px on click
            jQuery('#top').on('click', function() {
                jQuery('top').tooltip('hide');
                jQuery('body,html').animate({
                    scrollTop: 0
                }, 800);
                return false;
            });

            /*------------------------
            Accordion
            --------------------------*/
            jQuery('.iq-accordion .iq-ad-block .ad-details').hide();
            jQuery('.iq-accordion .iq-ad-block:first').addClass('ad-active').children().slideDown('slow');
            jQuery('.iq-accordion .iq-ad-block').on("click", function() {
                if (jQuery(this).children('div').is(':hidden')) {
                    jQuery('.iq-accordion .iq-ad-block').removeClass('ad-active').children('div').slideUp('slow');
                    jQuery(this).toggleClass('ad-active').children('div').slideDown('slow');
                }
            });

            /*------------------------
            Header
            --------------------------*/
            jQuery(window).on('scroll', function() {
                if (jQuery(this).scrollTop() > 10) {
                    jQuery('header').addClass('menu-sticky');
                } else {
                    jQuery('header').removeClass('menu-sticky');
                }
            });

            /*------------------------
            Magnific Popup
            --------------------------*/
            jQuery('.popup-gallery').magnificPopup({
                delegate: 'a.popup-img',
                type: 'image',
                tLoading: 'Loading image #%curr%...',
                mainClass: 'mfp-img-mobile',
                gallery: {
                    enabled: true,
                    navigateByImgClick: true,
                    preload: [0, 1] // Will preload 0 - before current, and 1 after the current image
                },
                image: {
                    tError: '<a href="%url%">The image #%curr%</a> could not be loaded.',
                  
                }
            });


            jQuery('.popup-youtube, .popup-vimeo, .popup-gmaps').magnificPopup({
                disableOn: 700,
                type: 'iframe',
                mainClass: 'mfp-fade',
                removalDelay: 160,
                preloader: false,
                fixedContentPos: false
            });

            jQuery('.popup-with-form').magnificPopup({
                type: 'inline',
                preloader: false,
                focus: '#name',

                // When elemened is focused, some mobile browsers in some cases zoom in
                // It looks not nice, so we disable it:
                callbacks: {
                    beforeOpen: function() {
                        if(jQuery(window).width() < 700) {
                            this.st.focus = false;
                        } else {
                            this.st.focus = '#name';
                        }
                    }
                }
            });



            jQuery(window).scroll(function() {
                var theta = jQuery(window).scrollTop() / 1000 % Math.PI;
                jQuery('#back-to-top a img, header .iq-img2 .logo2').css({
                    transform: 'rotate(' + theta + 'rad)'
                });

            });




            /*------------------------
            Owl Carousel
            --------------------------*/
            jQuery('.owl-carousel').each(function() {
                var jQuerycarousel = jQuery(this);
                jQuerycarousel.owlCarousel({
                    items: jQuerycarousel.data("items"),
                    loop: jQuerycarousel.data("loop"),
                    margin: jQuerycarousel.data("margin"),
                    nav: jQuerycarousel.data("nav"),
                    dots: jQuerycarousel.data("dots"),
                    autoplay: jQuerycarousel.data("autoplay"),
                    autoplayTimeout: jQuerycarousel.data("autoplay-timeout"),
                    navText: ["<i class='fa fa-angle-left fa-2x'></i>", "<i class='fa fa-angle-right fa-2x'></i>"],
                    responsiveClass: true,
                    responsive: {
                        // breakpoint from 0 up
                        0: {
                            items: jQuerycarousel.data("items-mobile-sm"),
                            nav: false,
                            dots: true
                        },
                        // breakpoint from 480 up
                        480: {
                            items: jQuerycarousel.data("items-mobile"),
                            nav: false,
                            dots: true
                        },
                        // breakpoint from 786 up
                        786: {
                            items: jQuerycarousel.data("items-tab")
                        },
                        // breakpoint from 1023 up
                        1023: {
                            items: jQuerycarousel.data("items-laptop")
                        },
                        1199: {
                            items: jQuerycarousel.data("items")
                        }
                    }
                });
            });

            /*Contact Form 7*/
            
        var getUrlParameter = function getUrlParameter(sParam) {
        var sPageURL = decodeURIComponent(window.location.search.substring(1)),
        sURLVariables = sPageURL.split('&'),
        sParameterName,
        i;
    for (i = 0; i < sURLVariables.length; i++) {
        sParameterName = sURLVariables[i].split('=');
        if (sParameterName[0] === sParam) {
            return sParameterName[1] === undefined ? true : sParameterName[1];
        }
    }
};
 
var VARIABLE = getUrlParameter('themename');
 
if (VARIABLE != null) {
     document.getElementById('productname').value = VARIABLE;
}

            /*------------------------
            Wow Animation
            --------------------------*/
            var wow = new WOW({
                boxClass: 'wow',
                animateClass: 'animated',
                offset: 0,
                mobile: false,
                live: true
            });
            wow.init();

            jQuery("#menu-icon").click(function(e) {
                e.preventDefault();
                jQuery("#mySidenav").toggleClass("slide-bar-menu");
            });

            /*--------------------------
               skrollr
            -----------------------------*/

            var s = skrollr.init();



        });

    });
})(jQuery);

class HoverButton {
  constructor(el) {
    this.el = el;
    this.hover = false;
    this.calculatePosition();
    this.attachEventsListener();
  }

  attachEventsListener() {
    window.addEventListener('mousemove', e => this.onMouseMove(e));
    window.addEventListener('resize', e => this.calculatePosition(e));
  }

  calculatePosition() {
    TweenMax.set(this.el, {
      x: 0,
      y: 0,
      scale: 1
    });

    const box = this.el.getBoundingClientRect();
    this.x = box.left + box.width * 0.5;
    this.y = box.top + box.height * 0.5;
    this.width = box.width;
    this.height = box.height;
  }

  onMouseMove(e) {
    let hover = false;
    let hoverArea = this.hover ? 0.7 : 0.5;
    let x = e.clientX - this.x;
    let y = e.clientY - this.y;
    let distance = Math.sqrt(x * x + y * y);
    if (distance < this.width * hoverArea) {
      hover = true;
      if (!this.hover) {
        this.hover = true;
      }
      this.onHover(e.clientX, e.clientY);
    }

    if (!hover && this.hover) {
      this.onLeave();
      this.hover = false;
    }
  }

  onHover(x, y) {
    TweenMax.to(this.el, 0.4, {
      x: (x - this.x) * 0.4,
      y: (y - this.y) * 0.4,
      scale: 1.15,
      ease: Power2.easeOut
    });

    this.el.style.zIndex = 10;
  }
  onLeave() {
    TweenMax.to(this.el, 0.7, {
      x: 0,
      y: 0,
      scale: 1,
      ease: Elastic.easeOut.config(1.2, 0.4)
    });

    this.el.style.zIndex = 1;
  }
}
var posX = posY = mouseX = mouseY = 0;
jQuery(window).load(function(e) {
  jQuery('body').trigger('mousemove');

  const btn1 = document.querySelector('.menu-icon');
  new HoverButton(btn1);
});



jQuery(function() {
  var prefix = function() {
    var a = window.getComputedStyle(document.documentElement, ""),
      b = (Array.prototype.slice.call(a).join("").match(/-(moz|webkit|ms)-/) || "" === a.OLink && ["", "o"])[1];
    return "WebKit|Moz|MS|O".match(new RegExp("(" + b + ")", "i"))[1], "-" + b + "-"
  }();
  jQuery(document).mousemove(function(e) {
    mouseX = e.pageX + 15;
    mouseY = e.pageY - jQuery(window).scrollTop() + 15;
    jQuery('.theBall-outer').attr('style', prefix + 'transform:translate(' + mouseX + 'px,' + mouseY + 'px)');
  });

  jQuery(document).on('mouseenter', 'a', '.menu-icon', function() {
    jQuery('.theBall').addClass('zooming');
  }).on('mouseleave', 'a', '.menu-icon', function() {
    jQuery(".theBall").removeClass("zooming")
  });
});
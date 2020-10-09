<template>
  <div class="Pose">
    <canvas width=1920 height=1080 id="toto"></canvas>
  </div>
</template>

<script>
export default {
  name: 'Pose',
  data: function() {
    return {
      vueCanvas: null
    }
  },
  mounted: function () {
      var canvas = document.getElementById('toto');
      var ctx = canvas.getContext('2d')
      ctx.strokeStyle = "#FF0000";

      /*
      //get DPI
      let dpi = window.devicePixelRatio;
  
      //get CSS height
      //the + prefix casts it to an integer
      //the slice method gets rid of "px"
      let style_height = +getComputedStyle(canvas).getPropertyValue("height").slice(0, -2);
      //get CSS width
      let style_width = +getComputedStyle(canvas).getPropertyValue("width").slice(0, -2);
      //scale the canvas
      canvas.setAttribute('height', style_height * dpi);
      canvas.setAttribute('width', style_width * dpi);*/

      this.vueCanvas = ctx;
      this.vueCanvas.fillStyle = "#FF0000";
      this.vueCanvas.beginPath();

      this.vueCanvas.fillRect(1800, 100, 10, 10);
      this.vueCanvas.moveTo(1800, 100);

      this.vueCanvas.fillRect(160, 20, 10, 10);
      this.vueCanvas.lineTo(160,20);
      this.vueCanvas.moveTo(160, 20);

      this.vueCanvas.fillRect(170, 10, 10, 10);
      this.vueCanvas.lineTo(170,10);
      this.vueCanvas.moveTo(170, 10);

      this.vueCanvas.fillRect(180, 60, 10, 10);
      this.vueCanvas.moveTo(160, 20);
      this.vueCanvas.lineTo(180,60);
      this.vueCanvas.moveTo(180, 60);

      this.vueCanvas.fillRect(140, 60, 10, 10);
      this.vueCanvas.moveTo(160, 20);
      this.vueCanvas.lineTo(140,60);
      this.vueCanvas.moveTo(140, 60);

      
      
      this.vueCanvas.stroke();
  },
  methods: {
    draw() {
      /*
      this.vueCanvas.fillStyle = 'rgb(255, 0, 0)';
      this.vueCanvas.beginPath();
      this.vueCanvas.moveTo(50, 50);
      // tracer le trait
      this.vueCanvas.fill();
      */
    },
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #toto{
    z-index : 2;
    position:fixed;
    left:0;
    right: 0;
    top:0;
    bottom:0;
    width:100%;
    height:100%;
  }
</style>

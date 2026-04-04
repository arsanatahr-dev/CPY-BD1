<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
html, body {
  margin: 0;
  padding: 0;
  background: transparent;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.video-container {
  width: 100%;
  max-width: 480px; /* ini bikin kecil di HP */
  aspect-ratio: 16/9;
  background: transparent;
}
video {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>
</head>
<body>

<div class="video-container">
  <video id="video" autoplay muted playsinline></video>
</div>

<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<script>
var video = document.getElementById('video');
var videoSrc = 'https://cctv.bandungkab.go.id/222415253f05ef03ed61f23d001a1cb8/hls/dishub01/s0BPNnOcMS/s.m3u8';

if (Hls.isSupported()) {
  var hls = new Hls();
  hls.loadSource(videoSrc);
  hls.attachMedia(video);
} else if (video.canPlayType('application/vnd.apple.mpegurl')) {
  video.src = videoSrc;
}
</script>

</body>
</html>

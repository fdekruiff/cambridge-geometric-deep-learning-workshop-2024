<body>
    <h2>Adynalate Kinase Results</h2>
    <div class="container">
        <div class="video-wrapper">
            <h3>Ground Truth Geodesic</h3>
            <video id="video1" controls preload="auto">
                <source src="adk_geodesic_trajectory.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <h3>Approximate Geodesic</h3>
            <video id="video2" controls preload="auto">
                <source src="adk_geodesic.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <h3>Linear Interpolation</h3>
            <video id="video3" controls preload="auto">
                <source src="adk_linear.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
    <div class="container">
        <div class="video-wrapper">
            <h3>Ground Truth Trajectory</h3>
            <video id="embedded_video1" controls preload="auto">
                <source src="adk_trajectory.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <h3>Low-Rank Approximation</h3>
            <video id="embedded_video2" controls preload="auto">
                <source src="adk_low_rank_approximation.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            var video1 = document.getElementById('video1');
            var video2 = document.getElementById('video2');
            var video3 = document.getElementById('video3');
            var embeddedVideo1 = document.getElementById('embedded_video1');
            var embeddedVideo2 = document.getElementById('embedded_video2');
            var videosReady = [false, false, false];
            var delayBeforeStart = 1000;
            var delayAfterFinish = 1000;
            function checkAndPlayVideos() {
                if (videosReady.every(function(value) { return value; })) {
                    setTimeout(function() {
                        video1.currentTime = 0;
                        video2.currentTime = 0;
                        video3.currentTime = 0;
                        video1.play();
                        video2.play();
                        video3.play();
                    }, delayBeforeStart);
                }
            }
            function playEmbeddedVideos() {
                setTimeout(function() {
                    embeddedVideo1.currentTime = 0;
                    embeddedVideo2.currentTime = 0;
                    embeddedVideo1.play();
                    embeddedVideo2.play();
                }, delayAfterFinish);
            }
            video1.onloadeddata = function() {
                videosReady[0] = true;
                checkAndPlayVideos();
            };
            video2.onloadeddata = function() {
                videosReady[1] = true;
                checkAndPlayVideos();
            };
            video3.onloadeddata = function() {
                videosReady[2] = true;
                checkAndPlayVideos();
                playEmbeddedVideos();
            };
        });
    </script>
</body>

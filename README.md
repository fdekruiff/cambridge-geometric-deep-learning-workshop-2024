<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ADK Videos</title>
    <style>
        .container {
            display: flex;
            justify-content: space-between;
        }
        .video-wrapper {
            flex: 1;
            margin-right: 1%;
        }
        .video-wrapper:last-child {
            margin-right: 0;
        }
        video {
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="video-wrapper">
            <h3>ADK Trajectory</h3>
            <video id="video1" controls>
                <source src="adk_trajectory.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
        <div class="video-wrapper">
            <h3>ADK Low Rank Approximation</h3>
            <video id="video2" controls>
                <source src="adk_low_rank_approximation.mp4" type="video/mp4">
                Your browser does not support the video tag.
            </video>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            var video1 = document.getElementById('video1');
            var video2 = document.getElementById('video2');

            var videosReady = [false, false];
            var delayInMilliseconds = 3000; // 3 seconds delay

            function checkAndPlayVideos() {
                if (videosReady[0] && videosReady[1]) {
                    video1.currentTime = 0;
                    video2.currentTime = 0;
                    setTimeout(function() {
                        video1.play();
                        video2.play();
                    }, delayInMilliseconds);
                }
            }

            video1.onloadeddata = function() {
                videosReady[0] = true;
                checkAndPlayVideos();
            };

            video2.onloadeddata = function() {
                videosReady[1] = true;
                checkAndPlayVideos();
            };
        });
    </script>
</body>
</html>

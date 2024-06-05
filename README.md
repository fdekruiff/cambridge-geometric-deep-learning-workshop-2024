<div style="display: flex; justify-content: space-between;">
    <video id="video1" width="48%" controls>
        <h3> Ground Truth Trajectory</h3>
        <source src="adk_trajectory.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <video id="video2" width="48%" controls>
        <h3> Low-Rank Approximation</h3>
        <source src="adk_low_rank_approximation.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
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

<div style="display: flex; justify-content: space-between;">
    <video id="video1" width="48%" controls>
        <source src="adk_trajectory.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <video id="video2" width="48%" controls>
        <source src="adk_low_rank_approximation.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        var video1 = document.getElementById('video1');
        var video2 = document.getElementById('video2');

        function playVideos() {
            video1.play();
            video2.play();
        }

        video1.onloadeddata = function() {
            if (video2.readyState >= 3) {
                playVideos();
            }
        };

        video2.onloadeddata = function() {
            if (video1.readyState >= 3) {
                playVideos();
            }
        };
    });
</script>

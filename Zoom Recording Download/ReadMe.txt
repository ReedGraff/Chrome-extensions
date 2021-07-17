**I am waiting on my chrome extension to be published, but If you need a zoom recording download immediately do the following:**
1. Open a Zoom recording link
2. Press CTRL +SHIFT + I
3. Open the console
4. Paste the following script:

setTimeout(function(){
    var video = document.getElementsByTagName('video')[0];
    var videoSource = video.getAttribute('src');
    var li = document.createElement('li');
    li.setAttribute('data-v-066c75dd', "");
    li.setAttribute('aria-label', "Download, 0 hours 0 minutes 0 seconds, Download button below");
    li.setAttribute('class', "transcript-list-item");
    li.setAttribute('id', "transcript-list-item-1");
    li.style.backgroundColor = 'rgb(229,105,105)';
    li.innerHTML = "<div data-v-066c75dd='' class='user-info'><div data-v-066c75dd='' class='avatar-wrapper has-hour'><img data-v-066c75dd='' src='https://st2.zoom.us/static/5.1.620/image/user.png' width='30' height='30' alt='user avatar' class='avatar'></div><div data-v-066c75dd='' class='user-name'><span data-v-066c75dd='' class='user-name-span'>Download</span><!----></div></div><div data-v-066c75dd='' class='timeline'><span data-v-066c75dd='' class='time'>00:00:00</span><span data-v-066c75dd='' class='text' id='Recording_Download'>Download this Recording</span><!----></div>"
    var textSection = document.querySelector('[aria-label="Audio Transcript List"]');
    textSection.insertAdjacentHTML('afterBegin', li.outerHTML);
    var link = document.createElement('a');
    link.setAttribute('href', videoSource)
    link.setAttribute('download', "download");
    link.setAttribute('id', 'download-button');
    link.innerHTML = "<div id='D-btn'>Download video - right click here and click [Save link as]...";
    var textSection = document.getElementById('Recording_Download');
    textSection.innerHTML = link.outerHTML;
    var downloadButton = document.getElementById('D-btn');
    downloadButton.style.backgroundColor = 'rgb(244,65,51)';
    downloadButton.style.border = 'none';
    downloadButton.style.borderRadius = "10px";
    downloadButton.style.textAlign = "center";
    downloadButton.style.color = 'white';
    downloadButton.style.textDecoration = 'none';
    downloadButton.style.cursor = 'pointer';
    link.style.cursor = 'pointer';
}, 2500);

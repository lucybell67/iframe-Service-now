# iframe-Service-now
simple web site
link to site: https://lucybell67.github.io/iframe-Service-now/

test

<a href="https://dev48352.service-now.com/incident_list.do?sysparm_query=active=true^caller_id=javascript:gs.getUserID()" class="link1">https://dev48352.service-now.com/incident_list.do?sysparm_query=active=true^caller_id=javascript:gs.getUserID()</a>
<iframe id="iframe1" src="about:blank" width="100%" scrolling="no"></iframe>
<script>
    var myLink = $('.link1');
    myLink.on('click', function(e){
        e.preventDefault(myLink);
        $('#iframe1').attr('src', myLink.attr('href'));
    });
    iFrameResize();
</script>

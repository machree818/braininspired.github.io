---
title: Contacts
description: Contacts
---
### Email:

> <a href='mailto:zhuyan@ibp.ac.cn'><i class="fa fa-envelope fa-2x"></i></a>

### Tel:
> +86-10-64888540

### Fax:
> +86-10-64871293

### Follow us on WeChat:

> ![WeChat](/images/wechat.webp)

### Location:
> Room 2203, NO.15, Datun Road
>
> Chaoyang District, Beijing, China (100101)

<div id="map" style="height: 20rem; width: 100%; max-width: 40rem;"></div>

<script>
    $.ajax({
        dataType: 'jsonp',
        url: 'https://www.google.com/jsapi',
        timeout: 1000,
        complete: function(obj,st) {
            mapjs = document.createElement("script");
            mapjs.type = "text/javascript";
            mapjs.async = true;
            mapjs.defer = true;
            if (obj.status == 200) {
                mapjs.src = "https://maps.googleapis.com/maps/api/js?key=AIzaSyCgrN3EuAV5ep3qUvV0Xo2Xpjvp91elL8I&callback=googleinitMap";
            } else {
                mapjs.src = "https://api.map.baidu.com/api?v=2.0&ak=2DZHIaUnG4oU5oLaVqmG9A91UFcz8bGY&callback=baiduinitMap";
            }
            document.body.appendChild(mapjs);
        }
    });
    function googleinitMap() {
        var uluru = {lat: 40.002939, lng: 116.376818};
        var map = new google.maps.Map(document.getElementById('map'), {
            zoom: 16,
            center: uluru
        });
        var marker = new google.maps.Marker({
            position: uluru,
            map: map
        });
    }
    function baiduinitMap(){
        var map = new BMap.Map("map");
        var point = new BMap.Point(116.38332,40.009132);
        map.centerAndZoom(point, 16);
        var marker = new BMap.Marker(point);
        var icon = marker.getIcon();
        icon.setSize(new BMap.Size(40,40));
        map.addOverlay(marker);
        var top_left_navigation = new BMap.NavigationControl();    
		map.addControl(top_left_navigation);
        var mapType = new BMap.MapTypeControl({mapTypes: [BMAP_NORMAL_MAP,BMAP_HYBRID_MAP]});
        map.addControl(mapType);
    }
</script>
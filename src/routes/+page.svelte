<svelte:head>
    <!-- UIkit CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/uikit@3.16.21/dist/css/uikit.min.css" />

    <!-- UIkit JS -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="/js/hijriDate.js"></script>
    <script type='text/javascript' src='//cdn.jsdelivr.net/jquery.marquee/1.3.1/jquery.marquee.min.js'></script>


</svelte:head>

<script>
    import { onMount } from 'svelte';
    import moment from 'moment/min/moment-with-locales';
    // import {moment as mm} from 'moment-hijri/moment-hijri';
    import 'hijri-date';


   
    onMount(async () => {
        import('$lib/uikit.js');
        import('$lib/uikit-icons.js');

        const now = new Date();
        const local_time= new moment();

       

        const geo = window.$.ajax({
            url: "https://geolocation-db.com/jsonp",
            jsonpCallback: "callback",
            dataType: "jsonp",
            success: function(location) {
                return location;
                // $('#country').html(location.country_name);
                // $('#state').html(location.state);
                // $('#city').html(location.city);
                // $('#latitude').html(location.latitude);
                // $('#longitude').html(location.longitude);
                // $('#ip').html(location.IPv4);
            },
            error: function (error) {
                console.log(error);
                return false;
            }
        });


        const athan = (async () => {
            
            try {

                let location = await geo;

                if (location) {
                    
                    local_time.locale(location.country_code || 'id');

                    // const response = await fetch('https://api.aladhan.com/v1/timingsByAddress/22-06-2023?address=Tangerang,ID&method=8&tune=2,3,4,5,2,3,4,5,-3');
                    const response = await fetch('https://api.aladhan.com/v1/timingsByCity/'+ moment(now).format('DD-MM-YYYY')+'?city='+ location.city + '&country='+ location.country_name +'&method=8&tune=2,3,4,5,2,3,4,5,-3');
                    console.log(location, local_time);
                    return response.json();
                }
            
            } catch (error) {
                console.log(error);
                return false;
            }
            
        })()
        
        let sholat = await athan;
        
        // console.log(sholat.data);
        document.getElementById('subuh').innerHTML = sholat.data.timings.Fajr;
        document.getElementById('terbit').innerHTML = sholat.data.timings.Sunrise;
        document.getElementById('dzuhur').innerHTML = sholat.data.timings.Dhuhr;
        document.getElementById('ashar').innerHTML = sholat.data.timings.Asr;
        document.getElementById('magrib').innerHTML = sholat.data.timings.Maghrib;
        document.getElementById('isya').innerHTML = sholat.data.timings.Isha;

       
        
        setInterval(updateClock, 1000);
        window.$('#date').hijriDate({
            showWeekDay: false,
            showGregDate: true,
            separator: '&nbsp;|&nbsp;',
            weekDayLang: 'id',
            hijriLang: 'id',
            gregLang: 'id',
            correction: +1
        });
        // window.addEventListener('load', Marquee('.marquee', 1))
        var widths = window.$('.marquee').width()
        var duration = widths * 15;

        window.$('.marquee').marquee({
            //speed in milliseconds of the marquee
            duration: duration, // for responsive/fluid use
            //duration: 8000, // for fixed container
            //gap in pixels between the tickers
            gap: window.$('.marquee').width(),
            //span in milliseconds before the marquee will start animating
            delayBeforeStart: 0,
            //'left' or 'right'
            direction: 'left',
            //true or false - should the marquee be duplicated to show an effect of continues flow
            duplicated: true
        });
    });

    function updateClock() {
        const arabic= new moment();
        arabic.locale('ar');

        const day = moment().format('dddd')
        const date = moment().format('ll')
        const date_hijr = arabic.format('ll')
        const hour = moment().format('H:mm:ss')
        const minute = moment().format('mm')
        const second = moment().format('ss')
        // document.getElementById('day').innerHTML = day;
        document.getElementById('hour').innerHTML = hour;
        // document.getElementById('minute').innerHTML = minute;
        // document.getElementById('second').innerHTML = second;
        // document.getElementById('date').innerHTML = date;
        // document.getElementById('date_hijr').innerHTML = date_hijr;

    }



</script>
<style>
blink {
  animation: blink 1s infinite
}

@keyframes blink {
  from {
    opacity: 0
  }

  to {
    opacity: 1
  }
}




</style>
<div class="uk-cover-container" uk-height-viewport>
    
    <div class="uk-inline uk-width-1-1" >
       

        <div class="uk-visible-toggle uk-light " tabindex="-1" uk-slideshow="animation: push;autoplay: true;autoplay-interval:10000" >
        
            <ul class="uk-slideshow-items "  uk-height-viewport>
                <li>
                    <img alt="slide" src="https://www.chasingthedonkey.com/wp-content/uploads/2022/01/Blue-mosque-in-Istanbul-at-sunset_Turkey_Depositphotos_45095187_S.jpeg"  uk-cover>
                </li>
                <!-- <li>
                    <video src="https://yootheme.com/site/images/media/yootheme-pro.mp4" autoplay loop muted playsinline  ></video>
                </li> -->
                <li>
                    <iframe title="video-slide" src="https://www.youtube-nocookie.com/embed/dGTEfbdZNv4?autoplay=1&amp;controls=0&amp;showinfo=0&amp;rel=0&amp;loop=1&amp;modestbranding=1&amp;wmode=transparent&amp;playsinline=1" width="1920" height="1080" allowfullscreen uk-cover></iframe>
                </li>
                <li>
                    <img alt="slide" src="https://media.islamicity.org/wp-content/uploads/2023/04/iStock-1185664054.jpg" uk-cover >
                </li>
                <li>
                    <img alt="slide" src="https://images.augustman.com/wp-content/uploads/sites/3/2022/04/06110718/stacey-franco-ex9kqrn1mj0-unsplash.jpeg"  uk-cover>
                </li>
                <li>
                    <img alt="slide" src="https://res.klook.com/images/fl_lossy.progressive,q_65/c_fill,w_1200,h_630/w_80,x_15,y_15,g_south_west,l_Klook_water_br_trans_yhcmh3/activities/aftgrrxg1sybkhnmuhae/Wisata%20Masjid%20Sheikh%20Zayed%20Abu%20Dhabi%20dan%20Museum%20Louvre%20dari%20Dubai.jpg"  uk-cover>
                </li>
                <li>
                    <img alt="slide" src="https://cdn.britannica.com/24/95924-050-002B40CB/Interior-Blue-Mosque-Istanbul.jpg"  uk-cover >
                </li>
                <li>
                    <img alt="slide" src="https://images.ctfassets.net/i01duvb6kq77/5xqClyoWgU9R7si6wvo745/c2e8397328b66c91fba0b822d2bef8d7/feature_Shah_Jahan_Mosque.jpg?w=1100&q=80&fm=jpg&fl=progressive"  uk-cover>
                </li>
            </ul>
        
            <!-- svelte-ignore a11y-missing-content -->
            <a class="uk-position-center-left uk-position-small uk-hidden-hover" href="!#" uk-slidenav-previous uk-slideshow-item="previous"></a>
            <!-- svelte-ignore a11y-missing-content -->
            <a class="uk-position-center-right uk-position-small uk-hidden-hover" href="!#" uk-slidenav-next uk-slideshow-item="next"></a>
        
        </div>

        
       
    </div>
    <div class="uk-grid-collapse uk-grid uk-position-cover uk-overlay uk-flex uk-flex-center uk-flex-top">
        <div class="uk-width-expand uk-text-left ">
            <div class="uk-padding-remove uk-light" style="height:125px;padding:1px;background-color:black;opacity:80%">
                <!-- <img src="https://seeklogo.com/images/M/masjid_assyakirin-logo-907E1F0265-seeklogo.com.png" width="50" height="50">
                <dl class="uk-description-list uk-description-list-divider">
                    <dt>Description term</dt>
                    <dd>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</dd>
                </dl> -->
                <!-- <div class="uk-child-width-1-3@m uk-child-width-1-2@s uk-grid" >
                    <div>
                        <img src="https://seeklogo.com/images/M/masjid_assyakirin-logo-907E1F0265-seeklogo.com.png" width="50" height="50">
                        <span class="uk-text-middle">Lorem ipsum.</span>
                    </div>
                
                </div> -->
                <div class="uk-flex-middle uk-grid" >
                    <div class="uk-width-expand" style="padding-left: 15px;">
                        <h2 class="uk-margin-remove-bottom">Masjid An Nur</h2>
                        <p class="uk-margin-remove-top uk-text-lead">Jl. Kp. Buaran No. 3 Lengkong Wetan Serpong Tangerang Selatan Banten 15323 Tlp. 2132132132132 @fdsafdsfdsaf</p>
                    </div>
                    <div class="uk-width-auto uk-flex-first ">
                        <img style="max-height:115px;margin:3px;" src="https://seeklogo.com/images/M/masjid_assyakirin-logo-907E1F0265-seeklogo.com.png"  alt="logo">
                    </div>
                </div>
            </div>
        </div>
        <div class="uk-width-1-3 ">
            <div class="uk-padding-remove uk-light uk-text-center "  style="height:125px;margin-left:0px;background-color:#10734d;opacity:90%" uk-grid>
                <!-- <div class="uk-width-1-2 uk-padding-small">
                    <span  class="uk-heading-medium text" id="day"></span>
                </div> -->

                <div class="uk-width-1-1 uk-padding-remove" style="font-size: 4rem;line-height: 70px;color:white;">
                    <span  class="uk-padding-remove" id="hour">00</span>
                    <!-- svelte-ignore a11y-distracting-elements -->
                    <!-- <blink class="uk-heading-medium">:</blink> -->
                    <!-- <span  class="uk-padding-remove" id="minute">00</span> -->
                    <!-- <span  class="uk-padding-remove" id="second">00</span> -->
                </div>
                <div class="uk-width-expand uk-padding-remove uk-margin-remove">
                    <span  class="uk-text-lead" style="color:#dedd87;" id="date"></span>
                </div>
            </div>
        </div>
        
        <div class="uk-position-bottom-center" style="width: 100%">
            
            <div class="uk-child-width-expand uk-grid-small uk-text-center uk-grid uk-grid" style="margin-bottom: 51px;max-height:115px"  >
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#10734d;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">SUBUH</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="subuh">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#10734d;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">TERBIT</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="terbit">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#10734d;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">DZUHUR</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="dzuhur">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#012e19;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">ASHAR</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="ashar">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#10734d;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">MAGRIB</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="magrib">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="">
                    <div class="uk-card uk-card-hover uk-height-1-1 " style="background-color:#10734d;opacity:85%">
                        <div class="uk-card-header uk-padding-remove">
                            <div class="uk-grid-small uk-flex-middle" uk-grid>
                                <div class="uk-width-expand">
                                    <h3 style="font-size: 2.5rem;color:white;" class="uk-card-title uk-margin-remove-bottom">ISYA</h3>
                                    <p class="uk-text-large" style="font-size: 3.5rem;color:#dedd87;margin-top: -27px;"><span id="isya">00:00</span></p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
            </div>  
            <div class="uk-position-bottom-center uk-overlay uk-overlay-default uk-padding-remove" style="width:100%;height:49px;">
                <div class="marquee">
                    <h2 class="uk-margin-remove">Shalat berjamaah lebih utama dibandingkan shalat sendirian dengan dua puluh tujuh derajat”. (HR. al-Bukhari dan Muslim)</h2>
                </div>
            </div>

            
        </div>
    </div>
    <!-- <div class="uk-position-bottom-left uk-overlay uk-overlay-primary" style="border-top-right-radius: 35px;">Bottom Left</div> -->
    <!-- <div class="uk-position-bottom-center uk-overlay uk-overlay-default uk-width-1-1"></div> -->
    <!-- <div class="uk-position-bottom-right uk-overlay uk-overlay-primary"  style="border-top-left-radius: 35px;">Bottom Right</div> -->
        
    
    
   
</div>

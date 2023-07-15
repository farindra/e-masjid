<svelte:head>
    <script src="https://www.google.com/recaptcha/api.js?onload=onloadCallback&render=explicit" async defer></script>
       <script>
        var onloadCallback = function() {
            alert("grecaptcha is ready!");
        };
       </script>
</svelte:head>
<script>
    import { onMount } from 'svelte';
        
    onMount(async () => {
       
        var form = document.getElementById('form-order');
        form.addEventListener('submit', function(e){
                        if ( "undefined" != typeof fbq ) {
                                        fbq("track",  "Lead", {"source": "loops.id","version": "1.3.4"});
                                }
                       
    
                                        
                        var data = {
                            content_type: 'product',
                            content_id: '98861',
                        };
    
                        if (document.getElementById("phone") != null) {
    
                            var phone = '';
                      
                            if ((phone = document.getElementById("phone").value.replace('0','+62')) !== '') {
                                ttq.identify({
                                    phone_number: phone.replace(/^0/, '+62'),
                                });
                            }
                        }
    
                        if (document.getElementById("email") != null) {
    
                            var email = '';
    
                            if ((email = document.getElementById("email").value) !== '') {
                                ttq.identify({
                                    email: email,
                                });
                            }
                        }
    
                        
                        ttq.instance('CID8LNBC77U4TTM9NOLG').track('SubmitForm', data);
        
                                         
        });
    });
</script>
<div>
<style>
    .loops-group { display: block; margin-bottom: 20px; }
    .loops-group label { font-weight: bold; }
    .loops-group input { display: block; width: 100%; height: 36px; border: 1px solid #ccc; border-radius: 3px; }
    .loops-group textarea { display: block; width: 100%; border: 1px solid #ccc; border-radius: 3px; }
    .loops-group input.loops-submit { background: #81bd4b; color: #fff; }
    .loops-footer { font-size: 11px; color: #ccc; font-style: italic; }
    .red { color: #B30000; }
</style>

<form id="form-order" class="loops-forms" action="https://staging.loops.id/save-order/form-1473" method="POST">
                            <div class="loops-group">
            <label for="phone">No HP <span class="red">*</span></label>
                        <input type="text" id="phone" name="phone" value="" placeholder="Sebutkan nomor HP aktif Anda: contoh 081234567890" pattern="[0]{1}[0-9]{8,12}" required>
                    </div>
    <div class="loops-group">
        <div class="g-recaptcha" data-sitekey="6Lc3C5AdAAAAAMHMFCvlwgRibEerTtlZe1lEdRW_"  ></div>
        <input type="submit" value="buy now" class="loops-submit">
    </div>
    <input type="hidden" id="current" name="current" value="">
    <input type="hidden" name="redirect" value="">
    <input type="hidden" name="_loops_nonce" value="">
    <p class="loops-footer">Powered by <a href="https://loops.id/?utm_source=form-embed&utm_content=98861">Loops.id</a>.</p>
</form>

</div>
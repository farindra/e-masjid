
<svelte:head>
	<link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-rc.0/dist/css/select2.min.css" rel="stylesheet" />
    <link href="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/0.8.2/css/flag-icon.min.css" rel="stylesheet" />
    <script src="https://code.jquery.com/jquery-3.2.1.min.js" integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-rc.0/dist/js/select2.min.js"></script>
    <style>
        .select2-container--default .select2-selection--single .select2-selection__rendered {
            text-align:center;
        }
    </style>
    <style>
        .loops-group { display: block; margin-bottom: 20px; }
        .loops-group label { font-weight: bold; }
        .loops-group input { display: block; width: 100%; height: 36px; border: 1px solid #ccc; border-radius: 3px; }
        .loops-group textarea { display: block; width: 100%; border: 1px solid #ccc; border-radius: 3px; }
        .loops-group input.loops-submit { background: #81bd4b; color: #fff; }
        .loops-footer { font-size: 11px; color: #ccc; font-style: italic; }
        .red { color: #B30000; }
    </style>
</svelte:head>

<script>
    import { onMount } from 'svelte';

onMount(() => {
   

        var form = document.getElementById('form-order');
        form.addEventListener('submit', function(e){
                    
        });

        let isoCountries = [
            {id: 93, code: 'AF', text: 'Afghanistan'},
            {id: 358, code: 'AX', text: 'Aland Islands'},
            {id: 355, code: 'AL', text: 'Albania'},
            {id: 213, code: 'DZ', text: 'Algeria'},
            {id: 1684, code: 'AS', text: 'American Samoa'},
            {id: 376, code: 'AD', text: 'Andorra'},
            {id: 244, code: 'AO', text: 'Angola'},
            {id: 1264, code: 'AI', text: 'Anguilla'},
            {id: 672, code: 'AQ', text: 'Antarctica'},
            {id: 1268, code: 'AG', text: 'Antigua And Barbuda'},
            {id: 54, code: 'AR', text: 'Argentina'},
            {id: 374, code: 'AM', text: 'Armenia'},
            {id: 297, code: 'AW', text: 'Aruba'},
            {id: 61, code: 'AU', text: 'Australia'},
            {id: 43, code: 'AT', text: 'Austria'},
            {id: 994, code: 'AZ', text: 'Azerbaijan'},
            {id: 1242, code: 'BS', text: 'Bahamas'},
            {id: 973, code: 'BH', text: 'Bahrain'},
            {id: 880, code: 'BD', text: 'Bangladesh'},
            {id: 1246, code: 'BB', text: 'Barbados'},
            {id: 375, code: 'BY', text: 'Belarus'},
            {id: 32, code: 'BE', text: 'Belgium'},
            {id: 501, code: 'BZ', text: 'Belize'},
            {id: 229, code: 'BJ', text: 'Benin'},
            {id: 1441, code: 'BM', text: 'Bermuda'},
            {id: 975, code: 'BT', text: 'Bhutan'},
            {id: 591, code: 'BO', text: 'Bolivia'},
            {id: 387, code: 'BA', text: 'Bosnia And Herzegovina'},
            {id: 267, code: 'BW', text: 'Botswana'},
            {id: 55, code: 'BV', text: 'Bouvet Island'},
            {id: 55, code: 'BR', text: 'Brazil'},
            {id: 246, code: 'IO', text: 'British Indian Ocean Territory'},
            {id: 673, code: 'BN', text: 'Brunei Darussalam'},
            {id: 359, code: 'BG', text: 'Bulgaria'},
            {id: 226, code: 'BF', text: 'Burkina Faso'},
            {id: 257, code: 'BI', text: 'Burundi'},
            {id: 855, code: 'KH', text: 'Cambodia'},
            {id: 237, code: 'CM', text: 'Cameroon'},
            {id: 1, code: 'CA', text: 'Canada'},
            {id: 238, code: 'CV', text: 'Cape Verde'},
            {id: 1345, code: 'KY', text: 'Cayman Islands'},
            {id: 236, code: 'CF', text: 'Central African Republic'},
            {id: 235, code: 'TD', text: 'Chad'},
            {id: 56, code: 'CL', text: 'Chile'},
            {id: 86, code: 'CN', text: 'China'},
            {id: 61, code: 'CX', text: 'Christmas Island'},
            {id: 672, code: 'CC', text: 'Cocos (Keeling) Islands'},
            {id: 57, code: 'CO', text: 'Colombia'},
            {id: 269, code: 'KM', text: 'Comoros'},
            {id: 242, code: 'CG', text: 'Congo'},
            {id: 242, code: 'CD', text: 'Congo, Democratic Republic of the Congo'},
            {id: 682, code: 'CK', text: 'Cook Islands'},
            {id: 506, code: 'CR', text: 'Costa Rica'},
            {id: 225, code: 'CI', text: 'Cote D\'Ivoire'},
            {id: 385, code: 'HR', text: 'Croatia'},
            {id: 53, code: 'CU', text: 'Cuba'},
            {id: 357, code: 'CY', text: 'Cyprus'},
            {id: 420, code: 'CZ', text: 'Czech Republic'},
            {id: 45, code: 'DK', text: 'Denmark'},
            {id: 253, code: 'DJ', text: 'Djibouti'},
            {id: 1767, code: 'DM', text: 'Dominica'},
            {id: 1809, code: 'DO', text: 'Dominican Republic'},
            {id: 593, code: 'EC', text: 'Ecuador'},
            {id: 20, code: 'EG', text: 'Egypt'},
            {id: 503, code: 'SV', text: 'El Salvador'},
            {id: 240, code: 'GQ', text: 'Equatorial Guinea'},
            {id: 291, code: 'ER', text: 'Eritrea'},
            {id: 372, code: 'EE', text: 'Estonia'},
            {id: 251, code: 'ET', text: 'Ethiopia'},
            {id: 500, code: 'FK', text: 'Falkland Islands (Malvinas)'},
            {id: 298, code: 'FO', text: 'Faroe Islands'},
            {id: 679, code: 'FJ', text: 'Fiji'},
            {id: 358, code: 'FI', text: 'Finland'},
            {id: 33, code: 'FR', text: 'France'},
            {id: 594, code: 'GF', text: 'French Guiana'},
            {id: 689, code: 'PF', text: 'French Polynesia'},
            {id: 262, code: 'TF', text: 'French Southern Territories'},
            {id: 241, code: 'GA', text: 'Gabon'},
            {id: 220, code: 'GM', text: 'Gambia'},
            {id: 995, code: 'GE', text: 'Georgia'},
            {id: 49, code: 'DE', text: 'Germany'},
            {id: 233, code: 'GH', text: 'Ghana'},
            {id: 350, code: 'GI', text: 'Gibraltar'},
            {id: 30, code: 'GR', text: 'Greece'},
            {id: 299, code: 'GL', text: 'Greenland'},
            {id: 1473, code: 'GD', text: 'Grenada'},
            {id: 590, code: 'GP', text: 'Guadeloupe'},
            {id: 1671, code: 'GU', text: 'Guam'},
            {id: 502, code: 'GT', text: 'Guatemala'},
            {id: 44, code: 'GG', text: 'Guernsey'},
            {id: 224, code: 'GN', text: 'Guinea'},
            {id: 245, code: 'GW', text: 'Guinea-Bissau'},
            {id: 592, code: 'GY', text: 'Guyana'},
            {id: 509, code: 'HT', text: 'Haiti'},
            {id: 509, code: 'HM', text: 'Heard Island & Mcdonald Islands'},
            {id: 39, code: 'VA', text: 'Holy See (Vatican City State)'},
            {id: 504, code: 'HN', text: 'Honduras'},
            {id: 852, code: 'HK', text: 'Hong Kong'},
            {id: 36, code: 'HU', text: 'Hungary'},
            {id: 354, code: 'IS', text: 'Iceland'},
            {id: 91, code: 'IN', text: 'India'},
            {id: 62, code: 'ID', text: 'Indonesia'},
            {id: 98, code: 'IR', text: 'Iran, Islamic Republic Of'},
            {id: 964, code: 'IQ', text: 'Iraq'},
            {id: 353, code: 'IE', text: 'Ireland'},
            {id: 44, code: 'IM', text: 'Isle Of Man'},
            {id: 972, code: 'IL', text: 'Israel'},
            {id: 39, code: 'IT', text: 'Italy'},
            {id: 1876, code: 'JM', text: 'Jamaica'},
            {id: 81, code: 'JP', text: 'Japan'},
            {id: 44, code: 'JE', text: 'Jersey'},
            {id: 962, code: 'JO', text: 'Jordan'},
            {id: 7, code: 'KZ', text: 'Kazakhstan'},
            {id: 254, code: 'KE', text: 'Kenya'},
            {id: 686, code: 'KI', text: 'Kiribati'},
            {id: 686, code: 'KR', text: 'Korea'},
            {id: 965, code: 'KW', text: 'Kuwait'},
            {id: 996, code: 'KG', text: 'Kyrgyzstan'},
            {id: 856, code: 'LA', text: 'Lao People\'s Democratic Republic'},
            {id: 371, code: 'LV', text: 'Latvia'},
            {id: 961, code: 'LB', text: 'Lebanon'},
            {id: 266, code: 'LS', text: 'Lesotho'},
            {id: 231, code: 'LR', text: 'Liberia'},
            {id: 218, code: 'LY', text: 'Libyan Arab Jamahiriya'},
            {id: 423, code: 'LI', text: 'Liechtenstein'},
            {id: 370, code: 'LT', text: 'Lithuania'},
            {id: 352, code: 'LU', text: 'Luxembourg'},
            {id: 853, code: 'MO', text: 'Macao'},
            {id: 853, code: 'MK', text: 'Macedonia'},
            {id: 261, code: 'MG', text: 'Madagascar'},
            {id: 265, code: 'MW', text: 'Malawi'},
            {id: 60, code: 'MY', text: 'Malaysia'},
            {id: 960, code: 'MV', text: 'Maldives'},
            {id: 223, code: 'ML', text: 'Mali'},
            {id: 356, code: 'MT', text: 'Malta'},
            {id: 692, code: 'MH', text: 'Marshall Islands'},
            {id: 596, code: 'MQ', text: 'Martinique'},
            {id: 222, code: 'MR', text: 'Mauritania'},
            {id: 230, code: 'MU', text: 'Mauritius'},
            {id: 262, code: 'YT', text: 'Mayotte'},
            {id: 52, code: 'MX', text: 'Mexico'},
            {id: 691, code: 'FM', text: 'Micronesia, Federated States of'},
            {id: 691, code: 'MD', text: 'Moldova'},
            {id: 377, code: 'MC', text: 'Monaco'},
            {id: 976, code: 'MN', text: 'Mongolia'},
            {id: 382, code: 'ME', text: 'Montenegro'},
            {id: 1664, code: 'MS', text: 'Montserrat'},
            {id: 212, code: 'MA', text: 'Morocco'},
            {id: 258, code: 'MZ', text: 'Mozambique'},
            {id: 95, code: 'MM', text: 'Myanmar'},
            {id: 264, code: 'NA', text: 'Namibia'},
            {id: 674, code: 'NR', text: 'Nauru'},
            {id: 977, code: 'NP', text: 'Nepal'},
            {id: 31, code: 'NL', text: 'Netherlands'},
            {id: 599, code: 'AN', text: 'Netherlands Antilles'},
            {id: 687, code: 'NC', text: 'New Caledonia'},
            {id: 64, code: 'NZ', text: 'New Zealand'},
            {id: 505, code: 'NI', text: 'Nicaragua'},
            {id: 227, code: 'NE', text: 'Niger'},
            {id: 234, code: 'NG', text: 'Nigeria'},
            {id: 683, code: 'NU', text: 'Niue'},
            {id: 672, code: 'NF', text: 'Norfolk Island'},
            {id: 1670, code: 'MP', text: 'Northern Mariana Islands'},
            {id: 47, code: 'NO', text: 'Norway'},
            {id: 968, code: 'OM', text: 'Oman'},
            {id: 92, code: 'PK', text: 'Pakistan'},
            {id: 680, code: 'PW', text: 'Palau'},
            {id: 970, code: 'PS', text: 'Palestinian Territory, Occupied'},
            {id: 507, code: 'PA', text: 'Panama'},
            {id: 675, code: 'PG', text: 'Papua New Guinea'},
            {id: 595, code: 'PY', text: 'Paraguay'},
            {id: 51, code: 'PE', text: 'Peru'},
            {id: 63, code: 'PH', text: 'Philippines'},
            {id: 64, code: 'PN', text: 'Pitcairn'},
            {id: 48, code: 'PL', text: 'Poland'},
            {id: 351, code: 'PT', text: 'Portugal'},
            {id: 1787, code: 'PR', text: 'Puerto Rico'},
            {id: 974, code: 'QA', text: 'Qatar'},
            {id: 262, code: 'RE', text: 'Reunion'},
            {id: 40, code: 'RO', text: 'Romania'},
            {id: 7, code: 'RU', text: 'Russian Federation'},
            {id: 250, code: 'RW', text: 'Rwanda'},
            {id: 590, code: 'BL', text: 'Saint Barthelemy'},
            {id: 290, code: 'SH', text: 'Saint Helena'},
            {id: 1869, code: 'KN', text: 'Saint Kitts And Nevis'},
            {id: 1758, code: 'LC', text: 'Saint Lucia'},
            {id: 590, code: 'MF', text: 'Saint Martin'},
            {id: 508, code: 'PM', text: 'Saint Pierre And Miquelon'},
            {id: 508, code: 'VC', text: 'Saint Vincent And Grenadines'},
            {id: 684, code: 'WS', text: 'Samoa'},
            {id: 378, code: 'SM', text: 'San Marino'},
            {id: 239, code: 'ST', text: 'Sao Tome And Principe'},
            {id: 966, code: 'SA', text: 'Saudi Arabia'},
            {id: 221, code: 'SN', text: 'Senegal'},
            {id: 381, code: 'RS', text: 'Serbia'},
            {id: 248, code: 'SC', text: 'Seychelles'},
            {id: 232, code: 'SL', text: 'Sierra Leone'},
            {id: 65, code: 'SG', text: 'Singapore'},
            {id: 421, code: 'SK', text: 'Slovakia'},
            {id: 386, code: 'SI', text: 'Slovenia'},
            {id: 677, code: 'SB', text: 'Solomon Islands'},
            {id: 252, code: 'SO', text: 'Somalia'},
            {id: 27, code: 'ZA', text: 'South Africa'},
            {id: 27, code: 'GS', text: 'South Georgia And Sandwich Isl.'},
            {id: 34, code: 'ES', text: 'Spain'},
            {id: 94, code: 'LK', text: 'Sri Lanka'},
            {id: 249, code: 'SD', text: 'Sudan'},
            {id: 597, code: 'SR', text: 'Suriname'},
            {id: 47, code: 'SJ', text: 'Svalbard And Jan Mayen'},
            {id: 268, code: 'SZ', text: 'Swaziland'},
            {id: 46, code: 'SE', text: 'Sweden'},
            {id: 41, code: 'CH', text: 'Switzerland'},
            {id: 963, code: 'SY', text: 'Syrian Arab Republic'},
            {id: 963, code: 'TW', text: 'Taiwan'},
            {id: 992, code: 'TJ', text: 'Tajikistan'},
            {id: 992, code: 'TZ', text: 'Tanzania'},
            {id: 66, code: 'TH', text: 'Thailand'},
            {id: 670, code: 'TL', text: 'Timor-Leste'},
            {id: 228, code: 'TG', text: 'Togo'},
            {id: 690, code: 'TK', text: 'Tokelau'},
            {id: 676, code: 'TO', text: 'Tonga'},
            {id: 1868, code: 'TT', text: 'Trinidad And Tobago'},
            {id: 216, code: 'TN', text: 'Tunisia'},
            {id: 90, code: 'TR', text: 'Turkey'},
            {id: 7370, code: 'TM', text: 'Turkmenistan'},
            {id: 1649, code: 'TC', text: 'Turks And Caicos Islands'},
            {id: 688, code: 'TV', text: 'Tuvalu'},
            {id: 256, code: 'UG', text: 'Uganda'},
            {id: 380, code: 'UA', text: 'Ukraine'},
            {id: 971, code: 'AE', text: 'United Arab Emirates'},
            {id: 44, code: 'GB', text: 'United Kingdom'},
            {id: 1, code: 'US', text: 'United States'},
            {id: 1, code: 'UM', text: 'United States Outlying Islands'},
            {id: 598, code: 'UY', text: 'Uruguay'},
            {id: 998, code: 'UZ', text: 'Uzbekistan'},
            {id: 678, code: 'VU', text: 'Vanuatu'},
            {id: 58, code: 'VE', text: 'Venezuela'},
            {id: 84, code: 'VN', text: 'Viet Nam'},
            {id: 1284, code: 'VG', text: 'Virgin Islands, British'},
            {id: 1340, code: 'VI', text: 'Virgin Islands, U.s.'},
            {id: 681, code: 'WF', text: 'Wallis And Futuna'},
            {id: 212, code: 'EH', text: 'Western Sahara'},
            {id: 967, code: 'YE', text: 'Yemen'},
            {id: 260, code: 'ZM', text: 'Zambia'},
            {id: 263, code: 'ZW', text: 'Zimbabwe'}
        ];
        
        function formatCountry (country) {
            if (!country.id) { return country.text; }
             return window.$(
                '<span style="padding-right: 15px;" class="flag-icon flag-icon-'+ country.code.toLowerCase() +' flag-icon-squared"></span>' +
                '<span class="flag-text">'+ country.text+" (+"+ country.id + ")</span>"
            );
            return country;
        };

        window.$('#countries').select2({
            placeholder: "Pilih Negara",
            templateResult: formatCountry,
            data: isoCountries,
            width: '100%'
        });
        
        window.$("#countries").val(62).trigger('change');

        window.$('#countries').on('select2:select', function (e) {
            var code = e.params.data;
            window.$('#phone_code').val(code.id.toString());
        });

        window.$('#phone_code').on('change keydown paste input', function(e){
            
            if (isoCountries.some(item => item.id == e.target.value)) {
                window.$("#countries").val( e.target.value).trigger('change');

            } else {
                window.$('#countries').val('').trigger('change');
            }

        });

});
    
</script>

<form id="form-order" class="loops-forms" action="https://staging.loops.id/save-order/form-baru-6" method="POST">
    <div class="loops-group">
        <label for="name">Nama lengkap <span class="red">*</span></label>
        <input type="text" id="name" name="name" value="" placeholder="Tulis nama Anda" required>
    </div>
    <div class="loops-group">
        <label for="phone">Masukan No Hp <span class="red">*</span></label>
        
        <div class="" >
            <select class="form-input" id="countries" required>

            </select>
        </div>
        <div style="display: flex;align-items: center;">
            <span style="position: absolute;z-index: 1000;padding: 7px;">+</span>
            <input type="text"  style="width:65px;padding-left: 15px;" name="phone_code" id="phone_code" value="62"  pattern="[0-9]+">
            <input type="text" style="width:100%;" id="phone" name="phone" placeholder="" value="" pattern="[0-9]+" required>
        </div>
        
    </div>
    <div class="loops-group">
        <input type="submit" value="Beli Sekarang" class="loops-submit">
    </div>
    <input type="hidden" id="current" name="current" value="">
    <input type="hidden" name="redirect" value="">
    <input type="hidden" name="_loops_nonce" value="">
    <p class="loops-footer">Powered by <a href="https://loops.id/?utm_source=form-embed&utm_content=98857">Loops.id</a>.</p>
</form>

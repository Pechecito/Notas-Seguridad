### Descripcion
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921
### Solucion
Se hizo un curl de la peticion, cambiando el header que identifica al navegador que era el user agent, y lo cambie a picobrowser
```bash
curl 'https://jupiter.challenges.picoctf.org/problem/28921/flag' \
  -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7' \
  -H 'Accept-Language: en,es-MX;q=0.9,es;q=0.8' \
  -H 'Connection: keep-alive' \
  -b 'cf_clearance=WGW9G8WsgfQU8.7Bid6y3ZRs7uiWKf10ctrPopz2A14-1745203224-1.2.1.1-5zlMw1v4UV9jc.6TtSwPQI1XbRnOl5sxJvxuzd__ZtyQ6BBc.YOaBekdQdaSd7krQy5yS9sEwGvZ8Ne1lkcp63bIDy9ak25lu4hfm4huvXJqnJwf14UG4YoCiek5cbMTyMdZRur61IEHtCxsbLWDiCa5LvaZA.H5R8YQ4bxySTAEju0ewr3mHD8dUw6uJCFUIxp8_qny_3rmIdXzyixiEAapG.sDJ86VJ8NBx4grGNIeEHpotXtdylFujvYUQwOS.2n8UV34WJrfs.RDfci2FQv67hxodCeMMaHGtadT48GIYNSSXlIlibYMH55YXL4rho8iBMw0JSP9adpu4.w6gRV5iUf1rNgGecWBlhZbEZ0; _ga_BSZFGM3NWK=GS1.1.1745804852.11.0.1745804858.54.0.621424460; _ga=GA1.2.1942072109.1743531261; _gid=GA1.2.1282259462.1745804860; _ga_L6FT52K063=GS1.2.1745804861.18.1.1745807262.52.0.1646750184' \
  -H 'Referer: https://jupiter.challenges.picoctf.org/problem/28921/flag' \
  -H 'Sec-Fetch-Dest: document' \
  -H 'Sec-Fetch-Mode: navigate' \
  -H 'Sec-Fetch-Site: same-origin' \
  -H 'Sec-Fetch-User: ?1' \
  -H 'Upgrade-Insecure-Requests: 1' \
  -H 'User-Agent: picobrowser' \
  -H 'sec-ch-ua: "Chromium";v="134", "Not:A-Brand";v="24", "Google Chrome";v="134"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Linux"'
```

```html
<div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
            <!-- <p><a class="btn btn-lg btn-success" href="admin" role="button">Click here for the flag!</a> -->
            <!-- </p> -->
        </div>
```
### Tags

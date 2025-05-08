### Descripcion
[🥛](http://mercury.picoctf.net:29522/)
### Hints
Look at the problem category
### Solucion
Hacemos CTRL U, para inspeccionar como se llama la imagen, y entrar a ella mediante la url, para poder descargarla
Quisimos abrirlo, con diferentes programas, pero no dejaba
con la herramienta zsteg
```bash
❯ zsteg -a concat_v.png
/var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:369:in `prev_scanline_byte': stack level too deep (SystemStackError)
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `upto'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `decoded_bytes'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line/mixins.rb:17:in `prev_scanline_byte'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:377:in `prev_scanline_byte'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:319:in `block in decoded_bytes'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `upto'
	from /var/lib/gems/3.3.0/gems/zpng-0.4.5/lib/zpng/scan_line.rb:318:in `decoded_bytes'
	... 10225 levels...
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg.rb:26:in `run'
	from /var/lib/gems/3.3.0/gems/zsteg-0.2.13/bin/zsteg:8:in `<top (required)>'
	from /usr/local/bin/zsteg:25:in `load'
	from /usr/local/bin/zsteg:25:in `<main>'
```
Buscamos un fragmento del error, y nos dice que con esta variable, podemos proceder
```bash
export RUBY_THREAD_VM_STACK_SIZE=500000000
```
Y ya con esto volvemos a correr, resulta, que la imagen, si tiene guardado algo ahi 
```bash
❯ export RUBY_THREAD_VM_STACK_SIZE=500000000
❯ zsteg -a concat_v.png
imagedata           .. text: "\n\n\n\n\n\n\t\t"
b1,b,lsb,xy         .. text: "picoCTF{imag3_m4n1pul4t10n_sl4p5}\n"
b1,bgr,lsb,xy       .. /var/lib/gems/3.3.0/gems/zsteg-0.2.13/lib/zsteg/checker/wbstego.rb:41:in `to_s': stack level too deep (SystemStackError)
	from /var/lib/gems/3.3.0/gems/iostruct-0.5.0/lib/iostruct.rb:180:in `inspect'
```
### Tags
#esteganografia 

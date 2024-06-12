- Video střih bez konverze [[ffmpeg]]
  id:: 6669f331-140d-4575-a291-4adffe002656
	- ```bash
	  ffmpeg -i <vstupnisoubor> -c copy -ss 01:35:00 -to 02:00:50 vystup.mkv
	  ```
- Převod z videa na audio [[ffmpeg]]
  id:: 6669f331-e0ca-40f6-aadf-30b65e1dc781
	- ```bash
	  ffmpeg -i input.mkv output.mp3
	  ```
- Hromadné zmenšení obrázků se zachováním proporcí [[mogrify]]
	- ```bash
	  mogrify -verbose -resize '2048x2048>' *.jpg
	  ```
- Hromadný prefix souborů
	- ```bash
	  for f in * ; do mv -- "$f" "PREFIX_$f" ; done
	  ```
	- Varianta pro Enduro závody:
	  ```bash
	  for f in * ; do mv -- "$f" "1_$f" ; done
	  for f in * ; do mv -- "$f" "2_$f" ; done
	  ```
- Hromadný tisk pouze první stránka
	- ```bash
	  lpr *.pdf -o page-ranges=1
	  ```
- Konverze PDF do JPG
	- ```bash
	  pdftoppm -jpeg -r 150 vstupni.pdf vystupni-prefix
	  ```
- První strana z více PDF souborů
	- ```bash
	  find . -name '*.pdf' -exec pdftoppm -jpeg -r 150 {} covers/{} -singlefile \;
	  ```
- Přeformátování [[xml]] souboru
	- ```bash
	  xmllint --format <vstupni.xml> > <vystupni.xml>
	  ```
- Převod a ořez [[mp3]]
	- ```bash
	  mp3cut -o output.mp3 -t 00:01:47+000-00:01:57+000 input.mp3
	  ```
-
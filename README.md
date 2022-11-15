# moode-uk-stations
Tools for managing creation of UK Radio Station jsons in format required for [MoOde Audio](https://moodeaudio.org/)

**Excel - moode-metadata.xlsm - series of sheets to manage a master list of radio stations**

 - Sheet [Logo] - details logo filenames and station name, these must be
   the same
 - Sheet [stations] - metadata for UK radio streams, add your own here,
   note that this list isn't maintained
 - Sheet [master] - master station list (grey - formulas, cream - user updates)
 - Sheet [Export] - generate station_data.csv that will be used by main notebook to create an import zip for moOde import

**Jupyter Notebooks :-**
 - radiofeeds moode json.ipynb - main notebook for generating
 - fuzzy-matching.ipynb - utility notebook to aid identify
   matching logo names to station names

**Other files / folders :-**
 - stations.zip - sample moOde stations import zip generated from
   radiofeeds moode json notebook
 - moode-default.jpg -
 - 600x600 folder - store radio logo's on jpg or png format, recommended size 600x600, variation ok
 - playlist-images folder - image for playlist item

**moOde import commands etc.. :-**
 - sudo moodeutl -q "delete from cfg_radio where id >= '500'"
 - sudo python /var/www/util/station_manager.py --import
   /home/pi/stations.zip
 - sudo moodeutl -u | tee /home/pi/radio-online.txt

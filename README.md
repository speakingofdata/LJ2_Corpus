# LJ2_Corpus

### Harper Strickland, 2025

## Description:

This repository contains a speech corpus in the format of the popular [LJ Speech Dataset][1]. It includes 26,200 audio files, double the size of LJ Speech, with segmentation available in 12-, 24-, and 48-hours. It can be used in combination with LJ Speech to triple its size, compared with LJ Speech, or easily substituted into any model designed to use LJ Speech.

[1]: <https://keithito.com/LJ-Speech-Dataset/> "About LJ Speech"

The single speaker's voice is the same as LJ Speech. All texts are public domain nonfiction texts with audio recordings available from [LibriVox.org][2]. Selection decisions were made to maximize variety of subjects and authors, and downsampling reduced terms over-represented in the texts, as compared to modern word frequency.

[2]: <https://librivox.org/pages/about-librivox/> "About LibriVox"

**Audio file naming convention:**

	- `wavs1` subdirectory: `LJ1##-####.wav`
	- `wavs2` subdirectory: `LJ2##-####.wav`
	- `wavs3` subdirectory: `LJ3##-####.wav`
	- `wavs4` subdirectory: `LJ4##-####.wav`

**Segments:**

	- 12-hour: `wavs1`
	- 24-hour: `wavs1` + `wavs2`
	- 48-hour: `wavs1` + `wavs2` + `wavs3` + `wavs4`

## Summary Statistics Compared to LJ Speech:

segment     | files   | duration  | mean (sec) | min (sec) | max (sec) | sources | chapters | authors | max source (hours)
:---------- | ------: | --------: | ---------: | --------: | --------: | ------: | -------: | ------: | -----------------:
LJ Speech   | 13,100  | 23:55     | 6.57       | 1.11      | 10.10     | 7       | 50       | 7       | 10:34
LJ2 12-hour | 6,550   | 11:57     | 6.58       | 1.13      | 10.10     | 59      | 68       | 59      | 0:47
LJ2 24-hour | 13,100  | 23:55     | 6.58       | 1.11      | 10.10     | 61      | 135      | 74      | 1:01
LJ2 48-hour | 26,200  | 47:51     | 6.58       | 1.11      | 10.10     | 61      | 288      | 82      | 2:53


## Files:

- `metadata.csv`

	Includes file id (same as audio filename without `'.wav'`) and transcript for each selection, in the same format as LJ Speech.

- `metadata.zip`

	Compressed version of `metadata.csv`.

- `LV_books_data_LJ2.json`

	Original source metadata available via LibriVox's [API][4]: id number, title, description, language, copyright year, section/chapter count, urls (text source, rss, zip file, project, LibriVox), total time (h\:m\:s and seconds), authors (name and birth/death years).

[4]: <https://librivox.org/api/info> "LibriVox API documentation"

- `books_enrichment_LJ2.csv`

	Additional source metadata: LibriVox id number (primary key), updated title (if incomplete in LibriVox API), LibriVox recordings upload date, count and duration of sections read by Linda Johnson ('LJ').

- `sections_details_LJ2.csv`

	Additional details about each source chapter represented in the corpus: index (first 3 digits in filename), LibriVox id number (foreign key), section number, authors (some texts are compilations with different authors for each chapter), count of files in corpus, total duration of corpus audio files (minutes), count of files included in ['80 Excerpts'][5] Corpus.

[5]: <https://github.com/speakingofdata/80_Excerpts> "Access 80 Excerpts Repository"

- Audio recordings:
	- Audio files can be downloaded from [https://huggingface.co/datasets/speakingofdata/LJ2_Corpus](https://huggingface.co/datasets/speakingofdata/LJ2_Corpus "LJ2 Corpus Hugging Face Repository").





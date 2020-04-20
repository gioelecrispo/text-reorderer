# Text Reorderer

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gioelecrispo/text-reorderer/blob/master/text-reorderer.ipynb)


This notebook provides a method to reorder the sentences in a text, using BERT For Next Sentence Prediction.
It is an important NLP task, especially when you have some unordered text coming from different sources such as in Summarization o Multi-Summarization tasks.  

Example

```python
sentences =  [
    "famous thanks to the victories obtained during the first campaign of Italy, after the coup d'etat of the 18th brumaire (9 November 1799) he assumed power in france: he was first consul from November of that year to 18 May 1804, and emperor of the French, with the name of napoleon i (napoléon ier) from 2 December 1804 to 14 April 1814 and again from 20 March to 22 June 1815 .",
    "thanks to his system of alliances and a series of brilliant victories against European powers, he conquered and governed a large part of continental Europe, exporting the revolutionary ideals of social renewal and managing to control numerous kingdoms through people loyal to him (giuseppe bonaparte in spain , joachim murat in the kingdom of naples, girolamo bonaparte in westphalia, jean-baptiste jules bernadotte in the kingdom of sweden and luigi bonaparte in the kingdom of holland) .",
    "napoleon bonaparte (ajaccio, 15 august 1769 - longwood, sant'elena island, 5 may 1821) was a french politician and general, founder of the first french empire and protagonist of the first phase of european contemporary history called napoleonic age .",
    "great man of war, protagonist of over twenty years of campaigns in europe, napoleon was considered the greatest strategist in history by the military historian basil liddell hart, while the historian evgenij tàrle does not hesitate to define him `` the incomparable master of art of the war `` is `` the greatest of the great '' .",
    "in march 1815, stealthily abandoned the island, he landed in Golfe Juan, near Antibes and returned to Paris without encountering opposition, regaining power for the so-called << one hundred days >> period, until he was definitively defeated by the seventh coalition in the battle of Waterloo, 18 June 1815; he spent the last years of his life in exile on the island of Saint Helena, under the control of the British .",
    "napoleon was defeated in the battle of Leipzig by the European allies in October 1813 and he abdicated on April 4, 1814, and was exiled to the island of Elba : it marked the decline of his dominion over Europe .",
]
ordering = reorder_sentences(sentences)
reordered_sentences = [sentences[idx] for idx in ordering]
ordering, reordered_sentences
```


Output

```python
# Output
([2, 0, 1, 5, 4, 3],
 ["napoleon bonaparte (ajaccio, 15 august 1769 - longwood, sant'elena island, 5 may 1821) was a french politician and general, founder of the first french empire and protagonist of the first phase of european contemporary history called napoleonic age .",
  "famous thanks to the victories obtained during the first campaign of Italy, after the coup d'etat of the 18th brumaire (9 November 1799) he assumed power in france: he was first consul from November of that year to 18 May 1804, and emperor of the French, with the name of napoleon i (napoléon ier) from 2 December 1804 to 14 April 1814 and again from 20 March to 22 June 1815 .",
  'thanks to his system of alliances and a series of brilliant victories against European powers, he conquered and governed a large part of continental Europe, exporting the revolutionary ideals of social renewal and managing to control numerous kingdoms through people loyal to him (giuseppe bonaparte in spain , joachim murat in the kingdom of naples, girolamo bonaparte in westphalia, jean-baptiste jules bernadotte in the kingdom of sweden and luigi bonaparte in the kingdom of holland) .',
  'napoleon was defeated in the battle of Leipzig by the European allies in October 1813 and he abdicated on April 4, 1814, and was exiled to the island of Elba : it marked the decline of his dominion over Europe .',
  'in march 1815, stealthily abandoned the island, he landed in Golfe Juan, near Antibes and returned to Paris without encountering opposition, regaining power for the so-called << one hundred days >> period, until he was definitively defeated by the seventh coalition in the battle of Waterloo, 18 June 1815; he spent the last years of his life in exile on the island of Saint Helena, under the control of the British .',
  "great man of war, protagonist of over twenty years of campaigns in europe, napoleon was considered the greatest strategist in history by the military historian basil liddell hart, while the historian evgenij tàrle does not hesitate to define him `` the incomparable master of art of the war `` is `` the greatest of the great '' ."])
```
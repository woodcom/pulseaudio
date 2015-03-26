# One sentense #
This wiki has a brief introduction of my work on soft volume setting optimization.

# Introduction #

Pulseaudio has some aspects hotpots causing high cpu load usage, that's why many users complaining and dropped PA, that's really a shame. In fact, PA community had done much to make PA performance better.

Per my understanding, these items are throttles:
- resampler method
- streams mixer
- streams volume setting/changing




# Details #

Add your content here.  Format your content with:
  * **For resampler methods, there're many choices, you can select the proper one according to your request. The resampler is implemented in external speexdsp library, it's an opensource library, so i think there need extra effort to make optimization. The internal resampler methods are trivial, copy, peaks.**
  * For softvolume changes, it's bind with differents formats, such as u8, alaw, ulaw, s16ne/re. Note there's CPU specific SSE/MMX optimization already for s16ne/re, so maybe it's useless to do the optimization again. Anyway, the other formats can enjoy the effort. the final results show there's positive feedback, the volume setting test tool from Martten helped much. Patch will checked in later, also with some performance datas.
  * Headings, paragraphs, and lists
  * Automatic links to other wiki pages
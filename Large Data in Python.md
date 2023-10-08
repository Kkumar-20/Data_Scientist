he best way to do this is to use chunking.

def read_in_chunks(file_object, chunk_size=1024):
    """Lazy function (generator) to read a file piece by piece.
    Default chunk size: 1k."""
    while True:
        data = file_object.read(chunk_size)
        if not data:
            break
        yield data

f = open('really_big_file.dat')
for piece in read_in_chunks(f):
    process_data(piece)
As a note as you start to process large files moving to a map-reduce idiom may help as you'll be able to work on separate chunked files independently without pulling the complete data set into memory.

Share
Improve this answer
Follow
answered Jan 26, 2013 at 17:43
Matt Alcock's user avatar
Matt Alcock
12.4k1515 gold badges4545 silver badges6161 bronze badges
Add a comment
1

In python, if you use a file object as an iterator, you can read a file line by line without opening the whole thing in memory.

for line in open("huge_file.txt"):
    do_something_with(line)

# Song Streamer Project
--- 
### Description

This was a group project which resulted in an application that allows users to add songs to a list of songs. From there the user has the ability to then "listen" to that song for a specified duration, "favorite" the song with the greatest listen time, "show all" of the songs and their listen times and finally "remove" the song overall and from favorites. The songs are stored in two data strucutes. The first are two binary search trees, one sorted by song index and the other by song title. The second is a max heap which contains the songs duration. These three data strucutres combined allow for quick and efficent access to the songs when certain function need to be performed. 

As this was a group project, my part was working on the binary search trees and making sure that all of our pointers were in place and memory allocated and deallocated properly to avoid memory leaks.

--- 
### Issues Faced 
One of the challenges I faced during this project was trying to manage memory. In C++ managing memory is one of the tricker things to do and by the end of the project I wanted to make sure that I was getting a clean valgrind report. This took a lot of trial and error trying to figure out where I was leaking memory and which pointers I needed to fix and which allocations needed to be deleted. Currently the program does return a clean valgrind report so in the end the trial and errors paid off.

Another issue that I faced was trying to figure out how to structure the binary search tree. I originally has implemented a templated BST class but after some thought I realized that wouldn't be very useful so I ended up just creating two seperate BST classes, one for the song title and the other for the song index.

Figuring out how to implement remove in the BST was tricky. I had originally planned out a recursive way to do it, but I was having a hard time and did't have the time to figure out the issues so I swiched to an interative apporach and I got it working but it took a lot longer than I would've liked to figure out. 

The biggest issue faced in creating this project was having all of the data structures linked and talking to each other. This was a big issue early on as this was a group project so we were all kind of working on different parts and not communicating enough to be able to easily connect everything together. The end solution was to actully store pointers to song object in all if the data structures because that allowed for when one song object was updated, all of the song objects stored across the data strucures were also updated. It worked out nicely in the end. 

---
### Time Complexities
* **song** and **show_listen_time** work in **O(N)** time
* ***remove** works in **O(logN)** - remove may not exactly meet this requirement in the heap
* **favorite** works in **O(logN)**
* **listen** works in **O(logN)**

---
### How to run
Commands to run in the terminal after cloning
```
make
```
```
./listen_up
```
You will then be promted with the song menu which contains further instructions



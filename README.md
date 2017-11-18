# Ex3
Advanced Programming Ex3
Play type:
1. Ask user whether he wants to play as co-op or user vs AI.
  a. If the answer is co-op, send to function that runs co-op
  b. If the answer is AI, send to function that runs user play, the AI play in a while.

AI Algorithm:
  1. Get possible moves.
  2. AI is given a vector of possible moves.
  3. Check first if vector isn't empty.
  4. Send to Function A a reference of the vector, receive back a pointer to the move to play.
  5. AI play move Pointer
  6. Announce AI played move.
  
  
Function A: (Chooses a move to play by checking each move of the O player, to get the minimal points of the X player)
  1. Initialize a pointer to NULL, initialize an "int min" to max int value.
  2. For each move(use iterator):
    a. send to Function B (that receives a reference to the board + the current move to play.)
    Function B returns int value of (User - AI points) and insert into (temp int)
    b. If (temp < min) {
      min = temp;
      Pointer = vector(i)
      }
  3. Return Pointer to the move.
  
  
Function B: (Gets each O player move, then checks each X player move to get the max points X could possibly get from his moves)
  1. Use copy constructor to create a new gameBoard2.
  2. Send the play to "make move" function, along with the gameBoard2 reference
  3. Vector moves = get all possible next moves for player X.
  4. Initialize int MAX to the minimum int possible.
  5. For each move i in the vector {
    a. Use a copy constructor to create a new gameBoard3.
    b. Send to "make move" function, the gameBoard3 reference + the current i move.
    c. Send to function C the new gameBoard3 reference, receive back an INT of (User - AI points) as currentPoints
    d. If( currentPoints> MAX) {
       - Set Max as currentPoints
       }
  6. Return Max  ( The maximum points that the User can get from his moves, according to the current AI move)
 
    

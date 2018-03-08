# Checkers
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace Checkers
{
    class Game

    {
        
        //Add a method for requesting of players names
        //Add a method for who's turn is next.
        //Add a method for game ends.
        //Add a method for who won the game.
        static void Main(string[] args)
        {
            Console.WriteLine("Welcome to Checkers.");
            Console.WriteLine("What is 1st players name?");
            string entry1 = Console.ReadLine();
            Console.WriteLine("What is 2nd players name?");
            string entry2 = Console.ReadLine();
            int[,] table = new int[8, 8];
            for (int R = 0; R < 8; R++)
            {
                for (int B = 0; B < 8; B++) 
                {


                    if ((R + B) % 2 == 0)
                    {
                        table[R, B] = (int)PieceColor.Blue;
                    }
                    else
                    {
                        table[R, B] = (int)PieceColor.Green;
                        
                    }
                }
            }
            for (int R = 0; R < 8; R++)

            {

                for (int B = 0; B < 8; B++)
                {
                    if (table[R, B] == (int)PieceColor.Green)
                    {

                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.ForegroundColor = ConsoleColor.Red;
                   
                        Console.Write(" " + table[R, B] + " ");

                    
                        
                    
                       

                    }
                    else
                    {

                        Console.BackgroundColor = ConsoleColor.Red;
                        Console.ForegroundColor = ConsoleColor.Black;
                        Console.Write(" " +table[R, B] + " ");
                    }
                }
                Console.WriteLine();
                
            }

            Console.WriteLine(" " + entry1 + " Vs " + entry2);
            Console.BackgroundColor = ConsoleColor.Green;
            Console.Write("B");
            Console.BackgroundColor = ConsoleColor.Red;
            Console.ForegroundColor = ConsoleColor.White;
            Console.Write("R");
            Console.BackgroundColor = ConsoleColor.Black;
            Console.ForegroundColor = ConsoleColor.Blue;
            Console.Write("B");
            Console.ReadLine();
            Board board = new Board(8, 8);
            Point point = new Point(0, 2);
            bool isOnBoard = board.OnBoard(point);
            Console.WriteLine(isOnBoard);







            /*Request name for player 1.
             * Request name for player 2.
             * Give player 1 proper game map cordinates.
             * Request a move from player 1.
             * Move player 1 game piece, if no more moves are allowed player 2 takes there next move.  
             * Give player 2 proper game map cordinates.
             * Request a move from player 2.
             * Move player 2 game piece, if no more moves are allowed player 1 takes there next move.  
             * If player jumps an opponent remove the piece.
             * If player reaches the end of the board player piece can no longer move.
             * Game ends once player has removed all the opponents pieces or no more moves can be made.
             * 
             * */




        }
    }
    class Board
    {
        public readonly int Width;
        public readonly int Height;
        //Add a method for Presenting the board
        public Board(int width, int height)
        {
            Width = width;
            Height = height;

        }

        public bool OnBoard(Point point)
        {
            return point.X >= 0 && point.X < Width &&
                     point.Y >= 0 && point.Y < Height;
        }

    }
    class Player
    {
        //Add a method for requesting  a move.
        //Add a method for presenting game cordinates
        //Add a method for players turn has ended.
        //Add a method for who's turn is next
        //Add a method for pieces able to jump opponents pieces.
        //Add a method for removal of the pieces.
    }
    class Piece
    {
        //Add a method for requesting board cordinates.


    }
    class Point
    {
        public readonly int X;
        public readonly int Y;
        public Point(int x, int y)
        {
            X = x;
            Y = y;
        }
    }
    enum PieceColor
    {
        
        Red = 5,
        Blue = 3,
        Green = 7
        
    }
    enum PieceColor1
    {
        
    }
}

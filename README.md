# game
tic tac toe game in react JS
import React, { useState } from 'react'; 
    const TicTacToe = () => { 
     const [board, setBoard] = useState(Array(9).fill(null)); 
     const [currentPlayer, setCurrentPlayer] = userState('X'); 
     const [winner, setWinner] = useState(null);  
    const handleClick = (index) => { 
    if (board[index] || winner) {
     return; } 
     const newBoard =[...board]; 
    newBoard[index] =currentPlayer;
      setBoard(newBoard);  
    setCurrentPlayer((prevPlayer) => (prevplayer === 'X' ? '0' :'X'));  
    const win = checkWinner(newBoard); 
     if(win)  {  setWinner(currentPlayer); 
    }   
    ; 
     const resetGame = () => {  
     setBoard(Array(9).fill(null));  setCurrentPlayer('X');
       setWinner(null);  };  
    const checkWinner = (board) =>  {  
      const winningLines = [  [0,1,2], [3,4,5],  [6,7,8], [8,3,6], [0,3,6], [2,5,8], [1,4,7],[0,4,8], [2,4,6],  ];  for(let i =0; i< winningLines.length; i++)  {  
     const [a,b,c] = winningLines[i]; 
     if( board[a] && board[a] === board[b] && board[a] === board[c] )  
    {  return board[a];
     }
      }   
    return null;  
    };  
     return( 
    <div className = "container"> 
      <h1>TIC-TAC-TOE</h1>   
    <h2>{winner ? `PLAYER ${winner} WON !` : `PLAYER  ${cuurentPlayer} 'S TURN`}</h2>  
     <div className="board"> {board.map ((value, index) => (  
    <div  key ={index}  className ="square"   
    onclick={ () => handleclick(index) } >  
    {value}  
     </div> 
      ) ) }
    </div> 
    <button onclick = {resetgame}> RESET </button>  </div> 
     );  
     }; 

     
     export default TicTacToe ;

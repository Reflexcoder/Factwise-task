import Board from " . /Board";
import Info from " ./Info";
import "./App.css;
import { useState} from "react";
function App(){
const [reset, setReset]=useState(false);
const [winner, setWinner]=useState(" ");
const resetBoard= ()=>{
     setReset(true);
  };
  return(
        <div className="App">
        <div
            className={'winner ${
                winner !==" "?" " : "shrink"
                }'}
                >
                <div className="winner-text">{winner}</div>
                <button onClick={() => resetBoard()}>
                    Reset Board
                </button>
            </div>
            <Board 
                 reset={reset}
                 setReset={setReset}
                 winner={winner}
                 setWinner={setWinner}
            />
            <Info/>
          </div>
    );
 }
 export default App;

 import "./css/board.css;
 import { useState, use Effect ,useRef } from "react";
 const Board=({reset, setReset,winner,setWinner})=>{
 const[turn,setTurn}=useState(0);
 const [data,setData]=useState([
"",
 "",
 "",
 "",
 "",
 "",
 "",
 "",
 "",
 ]);
 const boardRef=useRef(null);
 const draw=(event,index)=>{
     if (data[index-1]==="" && winner===""){
        const current =turn===0?"X":"0");
        data[index-1]=current;
        event.target.innerText=current;
        setTurn(turn===0?1:0);
      }
    };
  useEffect(()=>{
     const checkRow=() => {
       let ans=false;
       for(let i=0;i<9;i+=3){
       ans != 
             data[i]===data[i+1] &&
              data[i]===data[i+2] &&
              data[i] !=="";
              }
              return ans;
          };
          const checkCol=()=>{
            let ans=false;
            for(let i=0;i<3;i++){
            ans!=
            data[i]===data[i+3] &&
              data[i]===data[i+6] &&
              data[i] !=="";
                }
              return ans;
          };
          const checkDiagonal=()=>{
          return(
          (data[0]===data[4] &&
            data[0]===data[8] &&
            data[0] !=="") ||
            (data[2]===data[4] &&
            (data[2]===data[6] &&
            data[2]!=="")
            );
            const checkTie=()=>{
            let count=0;
            data.foreach((cell)=>{
            if(cell!==""){
              count++;
              }
              });
              return count===9;
              };
              if(checkWin()){
              setWinner(
                turn===0
                ?" " Player 2 wins !"
                : "Player 1 Wins!"
                );
                }else if(checkTie()){
                      setWinner("it is a tie!");
                      }
                    });
                    return (
                      <div ref={boardRef} className="board">
                        <div
                            className="input input-1"
                            onClick={(e)=>draw(e,1)}
                            ></div>
                            <div
                                 className="input input-1"
                            onClick={(e)=>draw(e,1)}
                            ></div>
                           <div
                                className="input input-2"
                            onClick={(e)=>draw(e,2)}
                            ></div>
                           <div
                                className="input input-3"
                            onClick={(e)=>draw(e,3)}
                            ></div>
                           <div
                                className="input input-4"
                            onClick={(e)=>draw(e,4)}
                            ></div>
                           <div
                                className="input input-5"
                            onClick={(e)=>draw(e,5)}
                            ></div>
                           <div
                                className="input input-6"
                            onClick={(e)=>draw(e,6)}
                            ></div>
                           <div
                                className="input input-7"
                            onClick={(e)=>draw(e,7)}
                            ></div>
                           <div
                                className="input input-8"
                            onClick={(e)=>draw(e,8)}
                            ></div>
                          <div
                                className="input input-9"
                            onClick={(e)=>draw(e,9)}
                            ></div>
                           </div>
                );
          };
          export default Board;
          JAVASCRIPT
          import "./css/info.css";
          const Info=()=>{
            return(
             <div className="info">
               <div className="player1">Player1:X</div>
                <div className="player2">Player2:X</div>
                </div>
            );
          };
          export default Info;
          css
          *{
             -webliy-box-sizing:border-box;
             -moz-box-sizing:border-box;
             box-sizing: border-box;
             }
             ,argin: 0;
             font-family: -apple-system,BlinkMacSystemFont,
             "Segeo UI,"Roboto","Oxygen","Ubuntu",
             -webkit-font-smoothing:antialiased;
             -moz-osx-font-smoothing:grayscale;
          }
          code{
               font-family:source-code-pro,Menlo,Monaco,Consolas,
                  "Courier New",monospace;
                }
                .info{
                      width: 30vw;
                      display:flex;
                      justify-contemt:space-evenly;
                      align-items:whitesmoke;
                  }
                   .player{
                       border: 2px solid #f6546a;
                       border-radius:5%;
                       padding:0.5rem 0;
                       display:flex;
                       font-size:1.5rem;
                       justify-content:center;
                       aligh-items:center;
                       width:10vq;
                }
             
                            
                               
          
              
            
            
      
 
 
 

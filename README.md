# SgRiichi Database Recursive Rating Calculation Solution

## Description
This database consists of **4998 games** (totaling **37492 records**) grabbed from a live database with random **UIDs** assigned. This prototype demonstrates the **recursive calculation algorithm** used to compute ratings. It also includes **insert** and **delete** functions for SGRiichi daily tasks.

## Current Stage
The project is currently in the testing phase to ensure that the algorithm is **stable** and can meet daily user requirements. This includes:
- Deleting a specific game
- Re-calculating the ratings after the game has been deleted

**Stress testing** and **validation** are required before applying this prototype to a real database.

## To-Do
- **Stress Test**: Ensure the system can handle a high load.
- **Verify Rating Calculation**: Check the precision and stability of the ratings after a user interaction (deleting or inserting a game).
- **Threshold Testing**: Determine the maximum number of records the database can handle effectively.
- **Enhance MySQL Functions**: Implement more MySQL functions to meet user requirements before the final implementation.

## Functions Used
- **`CALL delete_game(int game_id)`**:  
   This function deletes a specific game and recursively re-calculates all the rating changes after the game gets deleted, including adjustments for all players involved, until the last recorded game.

- **`CALL insert_game(int player1_id, int player1_netscore, int player2_id, int player2_netscore, int player3_id, int player3_netscore, int player4_id, int player4_netscore)`**:  
   This function inserts a new game involving 4 players, including their IDs and netscores. After insertion, the database will automatically calculate the rating changes for all 4 players based on the game results.  
   **Note**: This function automatically assigns a player a **1500 rating** by default if the player’s first recorded game is inserted into the system.

## Installation
1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/sgriichi-database.git

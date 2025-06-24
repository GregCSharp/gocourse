package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {

	source := rand.NewSource(time.Now().UnixNano())
	random := rand.New(source)

	// random number btw 1 and 100
	target := random.Intn(100) + 1

	fmt.Println("Bienvenue au jeu ou il faut deviner")
	fmt.Println("L'ordinateur a choisi un chiffre entre 1 et 100, devine lequel!")

	var guess int
	for {
		fmt.Println("Ecris un nombre!")
		fmt.Scanln(&guess)

		// check if the guess is correct
		if guess == target {
			fmt.Println("Bravo tu as deviné")
			break
		} else if guess < target {
			fmt.Println("trop petit, devine un nombre plus grand")
		} else {
			fmt.Println("trop grand, devine un nombre plus petit")
		}
	}
}

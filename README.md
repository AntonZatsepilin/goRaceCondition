# raceCondition

go run -race main.go 

This example clearly shows the race condition

package main

import (
	"fmt"
	"time"
)

func main() {
	counter := 0
	for i := 0; i < 1000; i++ {
		go func() {
			counter++
		}()
	}
	time.Sleep(time.Second * 2)
	fmt.Println(counter)
}
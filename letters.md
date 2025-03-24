
💌 A Letter of Happiness: How I Stopped Rushing for the Train

Recently, I started reading the letters of Blaise Pascal and Pierre de Fermat. A kind person once told me that these letters could change the way I see the world. And you know what? They actually did.

In one of Pascal’s letters, he describes probability as an immutable force—like a rock that never changes. That made me pause and think: Why am I always in a rush?

I realized that I often find myself running—especially for the train. But after reflecting on probability, I saw a different perspective. Every time I step onto the platform, it's like rolling a die. Whether I run or walk, my chances of catching the train remain the same. Wow! It’s literally like rolling dice. 🎲
To test this idea, I wrote a simple program that simulates my arrival at the platform and calculates the probability of catching a train. Here's the code:


```
package main

import (
 "fmt"
 "math/rand"
 "time"
)

func main() {
 rand.Seed(time.Now().UnixNano()) 
 const threshold = 250 
 const totalSeconds = 300 
 const attempts = 10 

 for i := 0; i < attempts; i++ {
 appearing := rand.Intn(totalSeconds)
 if appearing > threshold {
 fmt.Printf("Appearing on the station at second %d, closer to a train\n", appearing)
 } else {
 fmt.Printf("Appearing on the station at second %d, no train close\n", appearing)
 }
 }
}
```


This simple probability model helped me see things differently. Whether I rush or take my time, probability remains the same.

✨ This realization significantly reduced my anxiety. I still respect those who run for the train—they have their own reasoning. But I’ve found a way to stay calm. Maybe this perspective can help you too?

What do you think? Are you ready to trust probability? 😌



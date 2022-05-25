=============================
Making Decisions 1 Demo Guide
=============================

Intro
=====

Intro
-----

- Have the students download the demo folder, it's just two blank files 

- Start with `varsAndConditionals` 

Vars and Loops
==============

- In this file, we'll be using variables, conditionals, and loops to play out a fight between Jon Snow and Jamie Lannister.

#. Create a variable for Jon and Jamie's attack strengths. 

    .. code:: javascript

        let jonSnowAttack = 25
        let jamieLannisterAttack = 35


#. Before the battle begins, Jon and Jamie decide to compare attack strengths to get insight into who might win this battle. Using an if-else statement, console.log who has the greater attack strength.

    .. code:: javascript

        if (jonSnowAttack > jamieLannisterAttack) {
            console.log("Jon Snow has better attack than Jamie Lannister")
        } else {
            console.log("Jamie Lannister has better attack than Jon Snow")
        }


#. What if we have a tie? Our code would actually give the win to Jamie, which is no good. Add in an else if to resolve this.

    .. code:: javascript

        if (jonSnowAttack > jamieLannisterAttack) {
            console.log("Jon Snow has better attack than Jamie Lannister")
        } else if (jamieLannisterAttack > jonSnowAttack){
            console.log("Jamie Lannister has better attack than Jon Snow")
        } else {
            console.log("Jon Snow and Jamie Lannister have the same attack")
        }


#. Jamie, knowing he is the superior, initiates a fight with Jon. Let's create some additional stats for Jon Snow so we can see how this plays out.

    .. code:: javascript

        let jonSnowHealth = 100
        let jonSnowDefense = 0


#. Jamie attacks first - use an if/else to determine if Jon Snow can survive the attack. If he does not, console.log "Jon Snow has been slain." Otherwise, condole.log Jon Snow's health.

    .. code:: javascript

        if (jonSnowHealth <= jamieLannisterAttack) {
            console.log("Jon Snow has been slain.")
        } else {
            jonSnowHealth -= jamieLannisterAttack  #.  OR jonSnowHealth = jonSnowHealth - jamieLannisterAttack
            console.log(`Jon Snow's health is down to ${jonSnowHealth}`)
        }


#. Jon Snow, adamant he does not want to fight Jamie (can you blame him?), picks up a shield to help defend himself. Increase Jon's defense by 25.

    .. code:: javascript

        defense += 25


#. Jamie attacks again - use an if/else to determine if Jon Snow can survive the attack. Make sure to account for Jon's defense. If he does not, console.log "Jon Snow has been slain." Otherwise, console.log Jon Snow's health.

    .. code:: javascript

        if (health <= jamieLannisterAttack - defense) {
            console.log("Jon Snow has been slain.")
        } else {
            health -= (jamieLannisterAttack - defense)
            console.log(`Jon Snow's health is down to ${health}`)
        }


#. One of the town's people, obviously wanting Jon Snow to win, throws Jon a health kit. This health kit can raise Jon's health by 50pts. However, Jon's health cannot exceed 100. Using an if else statement, raise Jon's health to the appropriate level.

    .. code:: javascript

        if ((jonSnowHealth + 50) >= 100 ) {
            jonSnowHealth = 100
        } else {
            jonSnowHealth += 50
        }


#. Jamie, realizing this might take a while to beat Jon, decides to flip a coin, and if the coin lands on heads, he will aim to take Jon's head. If it lands on tails, Jamie will allow Jon to run away. Create a variable called coinLandsHeads and set it equal to false. Then, using an if-else statement and the equality operator, handle the value of the flipped coin (handle for both true and false).

    .. code:: javascript

        let coinLandsHeads = false

        if (coinLandsHeads === true) {
            console.log("The fight continues.")
        } else {
            console.log("Jon is allowed to run away.")
        }


#. Demonstrate how you can use != to accomplish the same thing.

    .. code:: javascript

        if (coinLandsHeads !== false) {
            console.log("The fight continues.")
        } else {
            console.log("Jon is allowed to run away.")
        }



#. Let's see how this battle will play out if it continues. Create a for loop that will have Jamie attack Jon 5 times. Console log Jon Snow's health after each attack. 

    .. code:: javascript

        for(let i = 0; i < 5; i++){
            jonSnowHealth -= (jamieLannisterAttack - jonSnowDefense)
            console.log(`Jon Snow's health is ${jonSnowHealth}`)
        }


#. Now we will combine for loops and if statements. Add a condition to check if Jon Snow will survive 

    .. code:: javascript

        for(let i = 0; i < 5; i++){
            if (jonSnowHealth >= 0) {
                console.log(`Jon Snow has been slain`)
            } else {
                jonSnowHealth -= (jamieLannisterAttack - jonSnowDefense)
                console.log(`Jon Snow's health is ${jonSnowHealth}`)
            }
        }



#. Demonstrate a while loop that will have Jamie attack Jon until Jon is slain. You will need to comment out the above for loops for these to run properly. 

    .. code:: javascript

        while(jonSnowHealth > 0){
            jonSnowHealth -= (jamieLannisterAttack - jonSnowDefense)
            console.log(`Jon Snow's health is ${jonSnowHealth}`) 
        }


#. Add an if statement that will let us know that Jon Snow has been slain. 

    .. code:: javascript

        while(jonSnowHealth > 0){
            jonSnowHealth -= (jamieLannisterAttack - jonSnowDefense)
            console.log(`Jon Snow's health is ${jonSnowHealth}`) 
            if(jonSnowHealth <= 0){
                console.log(`Jon Snow has been slain`)
            }  
        }

GitHub
------

- run through initializing, adding, and committing
- Explain that we will sync your local repo up with your GitHub account so that you can have a remote backup of your repo.

Creating a Repo on GitHub
-------------------------
- go to your github account and select the 'New' button to create a new repository
- give your repository a name (I would also call this `Intro-Demo`)
- click 'create repository'

Linking Your Local Repo to Your Remote Repo
-------------------------------------------
- On your github page, you should see instructions on how to link an existing repo
- Step 1: git remote add origin {you url}
  - This is the url that your repo is going to link to
- Step 2: git branch -M main
  - This sets your default branch to 'main'
- Step 3: git push -u origin main
  - This pushes your local (your computer) main branch up to the main branch of the remote (GitHub) repo.
  - ``-u`` is only required the first time, when you are setting your initial upstream.
  - At this point, you should see a response in your command line tool letting you know that your repo was successfully pushed.
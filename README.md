## Welcome to ...

This website contains information about a Simulator of the logical deduction card-game Sleuth. This is a project for the Multi-Agent Systems course of 2016/2017. 

The application that we wrote can simulate a game of Sleuth with five AI Agents that play the game. The model of the game is based on S5<sub>(m)</sub> logic system and the agents will use their knowledge about the world and the knowledge of other agents to make decisions and win the game. The goal of this simulation is to show how the knowledge of the agents lead to the decisions that they make and how they use the information to alter their strategy. 

### Game Explanation
Sleuth is a logical deduction game in which you need to reason about the knowledge of your opponents. The game consists of a deck of Gem-Cards, each with three properties: Color, Type and Quantity (e.g. Red Diamond Solitaire). At the beginning of the game, one of these cards is removed from the deck: this is the hidden gem. The rest of the cards are divided amongst the players. Each player is dealt four Question-Cards, which they can use on their turn to ask questions to other players about their cards. Through logical deduction about the knowledge of the other players, players can discover what the hidden gem is and win the game. 

The deck of Gem-Cards consists of 36 unique cards that encompass all the possible combinations of Color (Red, Green, Yellow, Blue), Type (Diamond, Opal, Pearl) and Quantity (Solitaire, Pair, Cluster). There are three types of Question-Cards that the players can use to ask questions with: one-element, two-element and free-choice question cards. A one-element Question-Card contains one property (e.g. Red) and allows the player to ask another player for all of the Gem-Cards that he or she has that share that one property. Similarly, two-element Question-Card contain two properties (e.g. Red Solitaire), which players can use to ask for all of the Gem-Cards of another player that share both of these properties. The free-choice Question-Card can be used to ask either a one-element or a two-element question with properties that the player can choose him or herself. There are 10 one-element, 33 two-element and 11 free-choice Question-Cards.

In each round, the player whose turn it currently is can ask a question to one of the other players with the use of a Question-Card. The latter player has to respond by showing all of his cards that match the properties of the Question-Card to the former player. Apart from these two player themselves, no other player can see this exchange of information. After a question has been answered, the current player removes the used Question-Card from his hand and places back on the bottom of the deck, after which he draws a new Question-Card from the top of the deck. This is the end of that players turn. Players take turns in asking each other questions until one of the players can determine what the hidden gem is and subsequently win the game.   

### Model
The model that we created is based on S5<sub>(m)</sub> logic, which is a mixed modal logic system. In this system, the most basic propositions are the Gem-Card, where an occurrence of a Gem-Cards indicates that the Gem-Card is in the game, and thus _not_ the hidden gem. These propositions are abbreviated using the first letter of each of its properties, so for example the Red Diamond Solitaire is represented as RDS.

Each player has a set of knowledge about the world, which we refer to as the knowledge base of the player. The most basic pieces of knowledge that are contained in this knowledge base are called first-level knowledge. First-level knowledge is a combination of a player that the knowledge belongs to and the Gem-Card that this player knows is in the game. For example, if Player 1 knows that the Red Diamond Solitaire is still in the game, this is represented as K<sub>1</sub>(RDS). Due to Axiom A3 of the S5<sub>(m)</sub> logic system, this implies that this Gem-Card is not in the game: K<sub>1</sub>(RDS) $\rightarrow$ RDS.

The agents are also able to use higher-level knowledge, which is knowledge about knowledge. For example, Player 1 can know that Players 2 knows that the Red Diamond Solitaire is in the game: K<sub>1</sub>(K<sub>2</sub>(RDS)). More importantly, as will be discussed in the next section about the reasoning of the agents, this makes it possible for players to know that another player does not know a particular Gem-Card.

Additionally, all of the cards that the player does not know for certain, he or she holds for possible. This is represented as, for instance, M<sub>1</sub>(RDS), which states that Player 1 holds it for possible that the Red Diamond Solitaire is in the game, but it might also be the hidden gem. 

You can use the [editor on GitHub](https://github.com/RichardElderman/Sleuth/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/RichardElderman/Sleuth/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

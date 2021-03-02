# Who-wins-The-Big-Game
HackerEarth Machine Learning Challenge: The Big Game is the annual American football championship and one of the most celebrated events in the history of sports. It is not only one of the most-watched sports events across the globe, it also has the reputation of being the second-largest day in terms of food consumption in the US. Every fan eagerly waits for the Game Day to find out if their favorite team wins.

A sports betting firm has utilized the data augmentation technique to synthesize a data set of championship outcome of the Big Game's participants and other data. Your task is to generate a model to determine and classify whether a given team will win the championship or not.
Language Used: Python 3.x

IDE used: Jupyter Notebook 

Approach:

Data Cleaning: My first step was to get an idea about the data. 
The attribute Team_Value has categorical values, so I have encoded in an ordinal fashion. The same thing goes for the attribute Coach_Experience_Level.
The attribute Number_Of_Injured_Players should have contained numerical values but upon inspecting, I found itcontains numerical values written in words. 
Since the no. of unique values in the column is only 10, I changed the values to numerical ones.

Feature Engineering:

			Then I tried using RandomForestClassifier on all the features and noted down the online score.
      
			Next I tried noticing the variances among the attributes and eliminated the ones having low variance.
      
			Next I got the features having highest feature importances in RandomForestClassifier and eliminated the rest.
      
	    Thus I was left with 4 attributes.
      
Baseline Models Used:
			
      I tried LogisticRegression,RandomForestClassifier, XGBClassifier, SVC, Perceptron all separately and noted down the online score with each one of them.
Final Model:
			
      Next I tried with the VotingClassifier to ensemble some of the models together to try to get a better score.
      
			During this, the combination (XGB,RF,LogReg) with weights (1,3,1) respectively provided me with the best result.  
      
Evaluation Criteria:    
100*f1_score(actual_values,predicted_values,average='binary')

Score:

76.46730 on public data(50%)

75.987667 on private data(50%)

Secured a rank of 39th on the leaderboard.

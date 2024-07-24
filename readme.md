# QnA Forum (LLD practice)

## Objectives
 - A user can post questions 
 - Users can answer questions (or add another answer to answered question)
  - Users can upvote an answer or a question
  - Users can follow a question to stay updated on new answers
  - User can view a feed of hot questions, determine how to define 'hotness' of a question
  - User can view their asked questions and posted answers.  
  - Only the question submitter can mark answers as working for me.
  - Order of answers would be in this order 'works_for_me', 'upvote', 'time of creation'
  - Suggest similar questions that user may want to ask before posting a new question ( follow up)
  - The question and thier answers can have comments (follow up)

## Assumptions for me (Clarifications)
 - A question's content will have a title and a body.
 - An upvote does not mean the user is following the QnA entity.
 - I'm defining 'hotness' of a question as inverse proportional to time duration between 2 consecutive upvotes.
    - Drawback: New questions will not come up in the feed
    - To counter this, feed will have a shuffle of new questions with hot questions
    - Drawback: Single threaded in nature, case for 2 simultaneous upvotes
    - To counter this, we can think of an abstract bucket of upvotes coming with time. hotness will be calculated by difference of non-zero consecutive bucket weight.
 - No need of pagination

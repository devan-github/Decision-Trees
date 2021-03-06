# Decision Trees

## Other Splitting Criteria
1. There is another measure of **cost** used as a splitting criterion called **variance reduction**, research this method and then:
    a. Explain it conceptually
    b. Provide a formula for the calculation
    c. Provide an example of a type of data and a question when it would be appropriate to use this criterion when building a tree to predict

## Practice Reading R Documentation
2. Download the R documentation for the package [rpart](https://cran.r-project.org/web/packages/rpart/rpart.pdf). Identify paramaters that you can alter to *control* attributes of the stopping criterion. What are they?

## Practice Building Trees

3. Download the Assistments data set available [here](http://users.wpi.edu/~yutaowang/data/non_skill_builder_data_new.csv).
    a. Look at the code book below, choose variables from teh data set that you think will have an impact on student performance *at the level of the student*. Make a new data set with these variables
    b. Aggregate the data *by student* using your data wrangling skillz making sure that the variables are condensed in a meaningful way
    c. Create a tree that predicts student performanceusing rpart
    d. Change the stopping criterion and splitting function to generate different trees.
    e. Which is your best tree, how did you make that determination?
    
## Code Book
    
    order_id
        These id's are chronological, and refer to the id of the original problem log.

    assignment_id
        Two different assignments can have the same sequence id. Each assignment is specific to a single teacher/class.

    user_id
        The ID of the student doing the problem.

    assistment_id
        The ID of the ASSISTment. An ASSISTment consists of one or more problems.

    problem_id
        The ID of the problem.

    original
        1 = Main problem
        0 = Scaffolding problem

    correct
        1 = Correct on the first attempt
        0 = Incorrect on the first attempt, or asked for help.
        This column is often the target for prediction

    attempt_count
        Number of student attempts on this problem.

    ms_first_response
        The time in milliseconds for the student's first response.

    tutor_mode
        tutor, test mode, pretest, or posttest

    answer_type
        choose_1: Multiple choice (radio buttons)
        algebra: Math evaluated string (text box)
        fill_in: Simple string-compared answer (text box)
        open_response: Records student answer, but their response is always marked correct

    sequence_id
        The content id of the problem set. Different assignments that assign the same problem set will have the same sequence id.

    student_class_id
        The class ID.

    position
        Assignment position on the class assignments page.
    problem_set_type
        Linear - Student completes all problems in a predetermined order.
        Random - Student completes all problems, but each student is presented with the problems in a different random order.
        Mastery - Random order; and students must "master" the problem set by getting a certain number of questions (3 by default) correct in a row before being able to continue.

    base_sequence_id
        This is to account for if a sequence has been copied. This will point to the original copy, or be the same as sequence_id if it hasn't been copied.

    skill_id
        ID of the skill associated with the problem.
        For the skill builder dataset, different skills for the same data record are in different rows. This means if a student answers a multi skill question, this record is duplicated several times, and each duplication is tagged with one of the multi skills.
        For the non skill builder dataset, different skills for the same data record are in the same row, separated with comma.

    skill_name
        Skill name associated with the problem.
        For the skill builder dataset, different skills for the same data record are in different rows. This means if a student answers a multi skill question, this record is duplicated several times, and each duplication is tagged with one of the multi skills.
        For the non skill builder dataset, different skills for the same data record are in the same row, separated with comma.

    teacher_id
        The ID of the teacher who assigned the problem.

    school_id
        The ID of the school where the problem was assigned.
    hint_count
        Number of student attempts on this problem.
    hint_total
        Number of possible hints on this problem.
    overlap_time
        The time in milliseconds for the student's overlap time.
    template_id
        The template ID of the ASSISTment. ASSISTments with the same template ID have similar questions.
    answer_id
        The answer ID for multi-choice questions.
    answer_text
        The answer text for fill-in questions.
    first_action
        The type of first action: attemp or ask for a hint.
    bottom_hint
        Whether or not the student asks for all hints.
    opportunity
        The number of opportunities the student has to practice on this skill.
        For the skill builder dataset, opportunities for different skills of the same data record are in different rows. This means if a student answers a multi skill question, this record is duplicated several times, and each duplication is tagged with one of the multi skills and the corresponding opportunity count.
        For the non skill builder dataset, opportunities for different skills of the same data record are in the same row, separated with comma.
    opportunity_original
        The number of opportunities the student has to practice on this skill counting only original problems.
        For the skill builder dataset, original opportunities for different skills of the same data record are in different rows. This means if a student answers a multi skill question, this record is duplicated several times, and each duplication is tagged with one of the multi skills and the corresponding original opportunity count.
        For the non skill builder dataset, original opportunities for different skills of the same data record are in the same row, separated with comma.

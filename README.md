SBA 308: JavaScript Fundamentals

This project gauges the understanding of fundamental JavaScript concepts and the ability to apply these concepts in a practical manner. The script gathers data, processes it, and then outputs a consistent result as described by a specification.

Acknowledgements

PerScholas
Details

The code analyzes and transforms the data given such that the output of the program is an array of objects.

The four different types of data provided are:

A CourseInfo object, which looks like this: { "id": number,

"name": string, } An AssignmentGroup object, which looks like this: { "id": number, "name": string, // the ID of the course the assignment group belongs to "course_id": number, // the percentage weight of the entire assignment group "group_weight": number, "assignments": [AssignmentInfo], } Each AssignmentInfo object within the assignments array looks like this: { "id": number, "name": string, // the due date for the assignment "due_at": Date string, // the maximum points possible for the assignment "points_possible": number, } An array of LearnerSubmission objects, which each look like this: { "learner_id": number, "assignment_id": number, "submission": { "submitted_at": Date string, "score": number } }

The output (an array of objects) seach contains the following information in the following format:

{ // the ID of the learner for which this data has been collected "id": number, // the learner’s total, weighted average, in which assignments // with more points_possible should be counted for more // e.g. a learner with 50/100 on one assignment and 190/200 on another // would have a weighted average score of 240/300 = 80%. "avg": number, // each assignment should have a key with its ID, // and the value associated with it should be the percentage that // the learner scored on the assignment (submission.score / points_possible) <assignment_id>: number, // if an assignment is not yet due, it should not be included in either // the average or the keyed dictionary of scores }

If an AssignmentGroup does not belong to its course (mismatching course_id), the program throws an error, letting the user know that the input was invalid.

If an assignment is not yet due, it is not included in the results or the average. Additionally, if the learner’s submission is late (submitted_at is past due_at), 10 percent of the total points possible is deducted from their score for that assignment.

A function named getLearnerData() accepts these values as parameters, in the order listed: (CourseInfo, AssignmentGroup, [LearnerSubmission]), and returns the formatted result, which is an array of objects as described above.

Authors

www.github.com/tyouse11

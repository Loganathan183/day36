Queries:

1.Find all the topics and tasks which are thought in the month of October
ans : db.topics.find({date: {$gte: ISODate("2020-10-01"), $lte: ISODate("2020-10-31")}})

2.Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020
ans: db.company_drives.find({drive_date: {$gte: ISODate("2020-10-15"), $lte: ISODate("2020-10-31")}})


3.Find all the company drives and students who are appeared for the placement.
ans:db.company_drives.find({appeared_students: { $exists: true, $ne: []}})


4.Find the number of problems solved by the user in codekata
ans:db.tasks.countDocuments({user_id: userId, is_completed: true})


5.Find all the mentors with who has the mentee's count more than 15
ans:db.mentors.find({ mentee_count: { $gt: 15 }})


6.Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020
ans:db.attendance.countDocuments({session_date:{ $gte: ISODate("2020-10-15"), $lte: ISODate("2020-10-31")}, is_present: false})


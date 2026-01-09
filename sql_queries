create database student_teacher_advance
use student_teacher_advance

#creating a user table
create table user(
 user_id int auto_increment primary key,
 user_name varchar(100) unique,
 password varchar(100),
 role enum('ADMIN','TEACHER','STUDENT')
 );
 
 #creating a teachers table
 create table teachers(
  teacher_id int auto_increment primary key,
  teacher_name varchar(100),
  email varchar(100),
  department varchar(50),
  user_id int,
  foreign key (user_id) references user(user_id)
  );
  
  #creating a students table
  create table students(
   student_id int auto_increment primary key,
   student_name varchar(100),
   email varchar(50),
   class varchar(50),
   user_id int,
   foreign key (user_id) references user(user_id)
   );
   
   #creating courses table
   create table courses(
   course_id int auto_increment primary key,
   course_name varchar(50),
   teacher_id int,
   foreign key (teacher_id) references teachers(teacher_id)
   );
   
   
   #creating a marks table
   create table marks(
    marks_id int auto_increment primary key,
    student_id int,
    course_id int,
    marks int,
    foreign key (student_id)references students (student_id),
    foreign key (course_id) references courses(course_id)
    );
   
   
   #creating attendance table
   create table attendance(
    attendance_id int auto_increment primary key,
    student_id int,
    course_id int,
    status enum('PRESENT','ABSENT'),
    date date,
    foreign key (student_id) references students(student_id),
    foreign key (course_id) references courses(course_id)
    );

   #creaing triggers(marks ki limit )
   delimiter //
   create trigger check_marks
   before insert on marks
   for each row
   begin
		  if new.marks>100 then
             signal sqlstate '45000'  
             set message_text='Marks cannot be greater than 100';
          end if;
  end //
 
  delimiter ;
   
   
  #creating stored procedures
  delimiter //
  create procedure get_student_result(in sid int)
  begin 
     select s.student_name,c.course_name,m.marks
     from students s
     join marks m on s.student_id=m.student_id
     join courses c on m.course_id=c.course_id
     where s.student_id=sid;
 end //
 delimiter ;
  
#inserting into users table
insert into user(user_name,password,role)values
  ('admin1','admin123','ADMIN'),
  ('admin2','admin123','ADMIN'),
  ('admin3','admin123','ADMIN'),
  ('admin4','admin123','ADMIN'),
  ('admin5','admin123','ADMIN'),
  ('teacher1','teach123','TEACHER'),
('teacher2','teach123','TEACHER'),
('teacher3','teach123','TEACHER'),
('teacher4','teach123','TEACHER'),
('teacher5','teach123','TEACHER'),
('teacher6','teach123','TEACHER'),
('teacher7','teach123','TEACHER'),
('teacher8','teach123','TEACHER'),
('teacher9','teach123','TEACHER'),
('teacher10','teach123','TEACHER'),
('teacher11','teach123','TEACHER'),
('teacher12','teach123','TEACHER'),
('teacher13','teach123','TEACHER'),
('teacher14','teach123','TEACHER'),
('teacher15','teach123','TEACHER'),
('student1','stud123','STUDENT'),
('student2','stud123','STUDENT'),
('student3','stud123','STUDENT'),
('student4','stud123','STUDENT'),
('student5','stud123','STUDENT'),
('student6','stud123','STUDENT'),
('student7','stud123','STUDENT'),
('student8','stud123','STUDENT'),
('student9','stud123','STUDENT'),
('student10','stud123','STUDENT'),
('student11','stud123','STUDENT'),
('student12','stud123','STUDENT'),
('student13','stud123','STUDENT'),
('student14','stud123','STUDENT'),
('student15','stud123','STUDENT'),
('student16','stud123','STUDENT'),
('student17','stud123','STUDENT'),
('student18','stud123','STUDENT'),
('student19','stud123','STUDENT'),
('student20','stud123','STUDENT'),
('student21','stud123','STUDENT'),
('student22','stud123','STUDENT'),
('student23','stud123','STUDENT'),
('student24','stud123','STUDENT'),
('student25','stud123','STUDENT'),
('student26','stud123','STUDENT'),
('student27','stud123','STUDENT'),
('student28','stud123','STUDENT'),
('student29','stud123','STUDENT'),
('student30','stud123','STUDENT');


#inserting into teacher table
insert into teachers(teacher_name,email,department,user_id) values
 ('Rahul Sharma','rahul@gmail.com','CS',1),
('Neha Verma','neha@gmail.com','IT',2),
('harshu','harsh@gmail.com','it',3),
('Amit Kumar','amit@gmail.com','CS',4),
('Pooja Singh','pooja@gmail.com','ECE',5),
('Ankit Jain','ankit@gmail.com','ME',6),
('Sunita Rao','sunita@gmail.com','CS',7),
('Vikas Gupta','vikas@gmail.com','IT',8),
('Kavita Iyer','kavita@gmail.com','ECE',9),
('Rohit Malhotra','rohit@gmail.com','ME',10),
('Meena Das','meena@gmail.com','CS',11),

('Suresh Yadav','suresh@gmail.com','IT',12),
('Nidhi Kapoor','nidhi@gmail.com','ECE',13),
('Arjun Khanna','arjun@gmail.com','CS',14),
('Priya Mishra','priya@gmail.com','ME',15),
('Manoj Patil','manoj@gmail.com','IT',16),
('Rekha Joshi','rekha@gmail.com','CS',17),
('Deepak Chauhan','deepak@gmail.com','ECE',18),
('Rina Sen','rina@gmail.com','ME',19),
('Ashish Tiwari','ashish@gmail.com','CS',20),
('Shalini Gupta','shalini@gmail.com','IT',21),

('Naveen Bansal','naveen@gmail.com','ECE',22),
('Swati Agarwal','swati@gmail.com','CS',23),
('Gaurav Saxena','gaurav@gmail.com','ME',24),
('Ruchi Jain','ruchi@gmail.com','IT',25),
('Karan Malhotra','karan@gmail.com','ECE',26),
('Ayesha Khan','ayesha@gmail.com','CS',27),
('Tarun Arora','tarun@gmail.com','ME',28),
('Ishita Roy','ishita@gmail.com','IT',29),
('Hemant Verma','hemant@gmail.com','ECE',30),
('Pankaj Mishra','pankaj@gmail.com','CS',31),

('Seema Kulkarni','seema@gmail.com','ME',32),
('Alok Srivastava','alok@gmail.com','IT',33),
('Bhavna Mehta','bhavna@gmail.com','ECE',34),
('Rajat Aggarwal','rajat@gmail.com','CS',35),
('Monika Saini','monika@gmail.com','ME',36),
('Sanjay Patel','sanjay@gmail.com','IT',37),
('Nikita Shah','nikita@gmail.com','ECE',38),
('Vivek Pandey','vivek@gmail.com','CS',39),
('Komal Arora','komal@gmail.com','ME',40),
('Yogesh Rana','yogesh@gmail.com','IT',41),

('Anjali Saxena','anjali@gmail.com','ECE',42),
('Harish Mehta','harish@gmail.com','CS',43),
('Preeti Nair','preeti@gmail.com','ME',44),
('Dinesh Solanki','dinesh@gmail.com','IT',45),
('Sakshi Goyal','sakshi@gmail.com','ECE',46),
('Mahesh Kulkarni','mahesh@gmail.com','CS',47),
('Ritu Choudhary','ritu@gmail.com','ME',48),
('Kunal Oberoi','kunal@gmail.com','IT',49),
('Shweta Tripathi','shweta@gmail.com','ECE',50);




#inserting into students table
insert into students (student_name,email,class,user_id) values
('Aman Verma','aman@gmail.com','BCA',1),
('Rohit Sharma','rohit@gmail.com','BCA',2),
('Neha Gupta','neha@gmail.com','BCA',3),
('Anjali Singh','anjali@gmail.com','BCA',4),
('Kunal Mehta','kunal@gmail.com','BCA',5),
('Pooja Yadav','pooja@gmail.com','BCA',6),
('Saurabh Jain','saurabh@gmail.com','BCA',7),
('Nikita Agarwal','nikita@gmail.com','BCA',8),
('Rahul Khanna','rahulkh@gmail.com','BCA',9),
('Simran Kaur','simran@gmail.com','BCA',10),

('Arjun Malhotra','arjun@gmail.com','BCA',11),
('Sneha Mishra','sneha@gmail.com','BCA',12),
('Vivek Tiwari','vivek@gmail.com','BCA',13),
('Riya Saxena','riya@gmail.com','BCA',14),
('Aakash Verma','aakash@gmail.com','BCA',15),
('Mehul Bansal','mehul@gmail.com','BCA',16),
('Kriti Goyal','kriti@gmail.com','BCA',17),
('Yash Patel','yash@gmail.com','BCA',18),
('Divya Choudhary','divya@gmail.com','BCA',19),
('Mohit Rana','mohit@gmail.com','BCA',20),

('Isha Kapoor','isha@gmail.com','BCA',21),
('Manish Pandey','manish@gmail.com','BCA',22),
('Sakshi Arora','sakshi@gmail.com','BCA',23),
('Aditya Srivastava','aditya@gmail.com','BCA',24),
('Palak Jain','palak@gmail.com','BCA',25),
('Harsh Vardhan','harsh@gmail.com','BCA',26),
('Tanya Mittal','tanya@gmail.com','BCA',27),
('Ritesh Kumar','ritesh@gmail.com','BCA',28),
('Shubham Singh','shubham@gmail.com','BCA',29),
('Pallavi Joshi','pallavi@gmail.com','BCA',30),

('Abhishek Rawat','abhishek@gmail.com','BCA',31),
('Komal Saini','komal@gmail.com','BCA',32),
('Nitin Chauhan','nitin@gmail.com','BCA',33),
('Preeti Nair','preeti@gmail.com','BCA',34),
('Gaurav Saxena','gaurav@gmail.com','BCA',35),
('Rashmi Kulkarni','rashmi@gmail.com','BCA',36),
('Lakshay Arora','lakshay@gmail.com','BCA',37),
('Bhavya Malhotra','bhavya@gmail.com','BCA',38),
('Irfan Khan','irfan@gmail.com','BCA',39),
('Muskan Sharma','muskan@gmail.com','BCA',40),

('Deepak Solanki','deepak@gmail.com','BCA',41),
('Shreya Bose','shreya@gmail.com','BCA',42),
('Aditi Kulshrestha','aditi@gmail.com','BCA',43),
('Varun Oberoi','varun@gmail.com','BCA',44),
('Ruchi Verma','ruchi@gmail.com','BCA',45),
('Siddharth Nigam','siddharth@gmail.com','BCA',46),
('Payal Mathur','payal@gmail.com','BCA',47),
('Naveen Joshi','naveen@gmail.com','BCA',48),
('Tanvi Deshpande','tanvi@gmail.com','BCA',49),
('Keshav Sharma','keshav@gmail.com','BCA',50);


#inserting into courses table
insert into courses (course_name,teacher_id) values
('Database Systems',101),
('Operating Systems',102),
('Computer Networks',103),
('Database Systems',104),
('Database Systems',105),
('Computer Networks',106),
('Database Systems',107),
('Machine Learning',108),
('Computer Networks',109),
('Web Development',110),

('Database Systems',111),
('Computer Networks',112),
('Database Systems',113),
('Database Systems',114),
('Computer Networks',115),
('Database Systems',116),
('Database Systems',102),
('Python Programming',103),
('R Programming',104),
('Database Systems',105),

('Database Systems',106),
('Embedded Systems',107),
('Big Data Analytics',108),
('Blockchain Technology',109),
('Database Systems',110),
('Data Mining',111),
('Computer Networks',112),
('Database Systems',113),
('Operating System Lab',114),
('Database Systems',115),

('Database Systems',149),
('Computer Networks',113),
('Database Systems',113),
('Cyber Security Lab',114),
('Database Systems',115),
('Cloud Lab',116),
('Computer Networks',117),
('Database Systems',118),
('Machine Learning',119),
('Java Lab',110),

('Database Systems',111),
('Blockchain Lab',150),
('Database Systems',144),
('Embedded Systems Lab',111),
('Software Testing Lab',115),
('Database Systems',111),
('Digital Logic Lab',102),
('C Programming Lab',103),
('Computer Networks',104),
('Database Systems',105);

#inserting into attendance table
insert into attendance(student_id,course_id,status,date)values
(1,151,'Present','2024-01-01'),
(2,152,'Absent','2024-01-01'),
(3,153,'Present','2024-01-01'),
(4,154,'Present','2024-01-01'),
(5,155,'Absent','2024-01-01'),

(6,156,'Present','2024-01-02'),
(7,157,'Present','2024-01-02'),
(8,158,'Absent','2024-01-02'),
(9,159,'Present','2024-01-02'),
(10,160,'Present','2024-01-02'),

(11,161,'Absent','2024-01-03'),
(12,162,'Present','2024-01-03'),
(13,163,'Present','2024-01-03'),
(14,164,'Absent','2024-01-03'),
(15,165,'Present','2024-01-03'),

(16,166,'Present','2024-01-04'),
(17,167,'Absent','2024-01-04'),
(18,168,'Present','2024-01-04'),
(19,169,'Present','2024-01-04'),
(20,170,'Absent','2024-01-04'),

(21,171,'Present','2024-01-05'),
(22,172,'Present','2024-01-05'),
(23,173,'Absent','2024-01-05'),
(24,174,'Present','2024-01-05'),
(25,175,'Present','2024-01-05'),

(26,176,'Absent','2024-01-06'),
(27,177,'Present','2024-01-06'),
(28,178,'Present','2024-01-06'),
(29,179,'Absent','2024-01-06'),
(30,180,'Present','2024-01-06'),

(31,181,'Present','2024-01-07'),
(32,182,'Absent','2024-01-07'),
(33,183,'Present','2024-01-07'),
(34,184,'Present','2024-01-07'),
(35,185,'Absent','2024-01-07'),

(36,186,'Present','2024-01-08'),
(37,187,'Present','2024-01-08'),
(38,188,'Absent','2024-01-08'),
(39,189,'Present','2024-01-08'),
(40,190,'Present','2024-01-08'),

(41,191,'Absent','2024-01-09'),
(42,192,'Present','2024-01-09'),
(43,193,'Present','2024-01-09'),
(44,194,'Absent','2024-01-09'),
(45,195,'Present','2024-01-09'),

(46,196,'Present','2024-01-10'),
(47,197,'Absent','2024-01-10'),
(48,198,'Present','2024-01-10'),
(49,199,'Present','2024-01-10'),
(50,200,'Absent','2024-01-10');

 
#inserting into marks table
 insert into marks(student_id,course_id,marks) values
 (1,154,85),
 (2,169,78),
 (3,199,88),
 (4,155,72),
 (5,170,90),
(6,154,81),
(7,153,75),
(8,171,84),
(9,156,79),
(10,200,91),

(11,153,86),
(12,158,73),
(13,173,89),
(14,174,70),
(15,158,92),
(16,172,80),
(17,171,77),
(18,156,85),
(19,154,83),
(20,155,88),

(21,156,79),
(22,157,84),
(23,158,90),
(24,159,72),
(25,160,91),
(26,171,75),
(27,172,87),
(28,173,81),
(29,164,86),
(30,154,89),

(31,154,82),
(32,152,78),
(33,163,85),
(34,174,80),
(35,185,90),

(36,166,88),
(37,167,76),
(38,168,84),
(39,169,79),
(40,160,91),

(41,161,85),
(42,182,77),
(43,183,83),
(44,184,88),
(45,185,80),
(46,166,90),
(47,200,81),
(48,153,87),
(49,174,78),
(50,165,92);


#calling the procedure
call get_student_result(49);




proc report data=sashelp.class split=':';
column _all_;
define name/display 'Student :name';
define Sex/ display'Student :gender'  format=$15. ;
define age/group'Student age: in years';
define height/sum 'Studnet height :in cms';
define weight/sum 'Student weight :in  lbs';
break after age/skip summarize;
rbreak after/skip summarize dol dul;

compute  sex;
if Sex='F' then sex='Female';
else if Sex='M' then sex='Male';
endcomp;
run;

// Viết phần mềm quản lý sinh viên
// Sinh viên gồm các thông tin: MSSV, tên, điểm toán, điểm văn, điểm trung bình
// Cho phép nhập n sinh viên, xuất ra sinh viên có điểm toán cao nhất, điểm trung bình thấp nhất
// Sắp xếp các sinh viên theo điểm văn

let students = [];
function object_student(){
	student = {
  	name: "",
    id: "",
    pointofMath:"",
    pointofLiterature:"",
    average:""
  }
  student.name = prompt("Input the name");
  student.id = prompt("Input the ID:");
  student.pointofMath = Number(prompt("Input the math point:"));
  student.pointofLiterature = Number(prompt("Input the literature point:"));
  student.average = (student.pointofMath + student.pointofLiterature)/2
}

function array_student(){
  let numberInput = Number(prompt("Input the number:"));
  for(let i = 0; i < numberInput; i++)
	{
  	object_student();
    students.push(student);
  }
  console.log(students);
}

function maxMathPoint(){
  let max = 0; nameofStudent = "";
  for(let j = 0; j < students.length; j++)
  {
  	if (students[j].pointofMath > max)
    {
    	max = students[j].pointofMath;
      nameofStudent = students[j].name;
    }
  }
  console.log(`${nameofStudent} has max math point:${max}`);
}

function minAverage(){
  let min = 10, name = "";
  for (let k = 0; k < students.length; k++)
  {
  	if(students[k].average < min)
    {
    	min = students[k].average;
      name = students[k].name;
    }
  }
  console.log(`${name} has min average: ${min}`)
}

function arrange(){
	var diemvan = [];
  var ten = [];
  for (let d = 0; d < students.length; d++)
  {
  	diemvan.push(students[d].pointofLiterature);
    ten.push(students[d].name)
  }
  for (let m = 0; m < diemvan.length; m++)
  {
  	for (let n = m + 1; n < diemvan.length; n++)
    {
    	if(diemvan[m] > diemvan[n]){
        var temp = diemvan[m];
        diemvan[m] = diemvan[n];
        diemvan[n] = temp;
        var temp2 = ten[m];
        ten[m] = ten[n];
        ten[n] = temp2;
      }
    }
  }
  console.log(ten);
  console.log(diemvan);
}

array_student();
maxMathPoint();
minAverage();
arrange();


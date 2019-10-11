document.getElementById('title_banner')로 가져온 Object와
$('#title_banner')로 가져온 오브젝트는 서로 다르다

jquery에서 가져오는 __proto__는 Object이고
getElementById로 가져오는 __proto__는 HTMLTableSectionElement이다

$('#title_banner').empty()는 가능하나
document.getElementById('title_banner').empty()는 불가능하다

같은 맥락으로
document.getElementById('title_table').getElementById('title_banner')
document.getElementById('title_table')의 __proto__는 HTMLTableElement이다.
document.getElementById('title_table').getElementByTagName?이런류가 가능하다.

역시 불가능하다

테이블 안에 새로운 row를 추가하고 td를 넣어주는 것을 자바스크립트로 해주려고한다.

row = tbody.insertRow();
let cell_obj = row.insertCell(0);

cell_obj 는 HTMLTableCellElement이다 

createElement는 document.createElement를 해주고 해당 obj를 Cell에다가 붙여주는 작업을 해야 한다.
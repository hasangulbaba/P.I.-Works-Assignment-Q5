[comment]: <> (Only user tables should appear on the initial screen, if a new user is required to be registered, the registration page should be opened with the "+ New User" button and inputs should be entered, the input information entered should be recorded in the db.)
[comment]: <> (The page should consist of two parts, namely table and textfields, when the user enters the page, he/she must first encounter the table and see the registered users.)
<div class="clearfix">
[comment]: <> (If you want to login with the new user, the registration screen should appear when the "+ New User" button is clicked.)
<div id="NewUser" class="w-30 float-left"><button class="btn btn-info" type="button">+ New User</button></div>
<div class="w-30 float-left pl-3">
[comment]: <> (When the "Hide Disabled User" checkbox is clicked, the records that have the Disabled feature, that is, the Enabled checbox on the registration screen, must be defined in a way that they are not displayed in the user table.)
<div class="custom-control custom-checkbox"><input type="checkbox" class="custom-control-input" id=" HideDisabledUser "> <label for=" HideDisabledUser " class="custom-control-label">Hide Disabled User</label></div>
</div>
[comment]: <> (With the "Save User" button, the username, Displayname, phone, email, User Roles and enabled information entered on the registration page are saved in the database and should now be visible in the user table.)
[comment]: <> (If the Enabled checkbox is clicked, the user should not be visible in the table.)
<div class="w-30 float-right"><button class="btn btn-info" type="button" id="SaveUser" onclick="myFunction()">Save User</button></div>
</div>
<form class="row my-2">
<div class="col border">
[comment]: <> (A sample of table structure)
[comment]: <> (Tables should have filter property in columns. It should filterable and sortable according to id, username, email and Enabled properties. Example: "data tables")
[comment]: <> (The table rows should have the hover feature. When "mouse over" is used, the color should be blue.)
<table class="table table-striped table-bordered table-hover" id="myTable">
<thead class="table-primary ">
<tr>
<th>ID</th>
<th>User Name</th>
<th>Email</th>
<th>Enable</th>
</tr>
</thead>
<tbody>
<tr>
<td id="id">1</td>
<td>AdminUser</td>
<td>admin@piworks.net</td>
<td>true</td>
</tr>
<tr>
<td id="id">2</td>
<td>Test User</td>
<td>testuser@piworks.net</td>
<td>true</td>
</tr>
</tbody>
</table>
</div>
<div class="col border">
<div class="m-4 bg-dark" style="opacity: 0.2;">
### New User
</div>
<div class="form-group"><label for="name">Username</label> <input type="text" id="name" class="form-control" placeholder="Enter User Name"></div>
<div class="form-group"><label for=" DisplayName ">Display Name</label> <input type="text" id="DisplayName" class="form-control" placeholder="Enter Display Name"></div>
<div class="form-group"><label for="phone">Phone:</label> <input type="text" id="phone" class="form-control" placeholder="Enter Phone Number"></div>
<div class="form-group"><label for="email">Email</label> <input type="email" id="email" class="form-control" placeholder="Enter email address"> <small class="form-text text-muted">ex:PIWorks@....com</small> </div>
[comment]: <> (When the selectore named "User Roles" is clicked, it should not close the display of the checkbox named "enabled" under it.)
[comment]: <> ("User Roles" checkbox should has dropdown menu that include 'Guest','Admin' and 'Super Admin' user roles items.)
<div class="form-group"><label for=" UserRoles">User Roles</label> <select name="roles" id="UserRoles" class="form-control"><option value="Guest">Guest</option> <option value="Admin">Admin</option> <option value="SuperAdmin">SuperAdmin</option></select></div>
<div class="clearfix">
<div class="w-30 float-left">
Enabled :
</div>
<div class="w-30 float-left pl-2">
<div class="custom-control custom-checkbox"><input type="checkbox" class="custom-control-input" id="Enabled"> <label for="ch" class="custom-control-label"></label></div>
</div>
</div>
</div>
</form>
[comment]: <> (Sample script for filling the registration page in the table)
<script>var count = 3; function myFunction() { var a = []; a.push(count); a.push(document.getElementById("name").value) a.push(document.getElementById("email").value) a.push(document.getElementById("roles").value) for (var i = 0; i < a.length; i++) { console.log(a[i]); var x = document.createElement("TD"); var t = document.createTextNode(a[i]); x.appendChild(t); document.getElementById("myTr").appendChild(x); } count++; }</script>

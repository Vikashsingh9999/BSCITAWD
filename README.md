# BSCITAWD
Practical no. 03 
 
3a) Aim :- Create a simple web page with various server controls to demonstrate setting and use of their properties , Create a Registration form to demonstrate use of various Validation controls. 
 
Home.aspx (Run this file): Design: 
  
 
Login.aspx Design: 
  
 
Login.aspx.cs (Code behind): using System; 
using System.Collections.Generic; 
using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
namespace validation 
{ public partial class Login : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
 
} protected void btnlogin_Click(object sender, EventArgs e) 
{ if (txtname.Text == "ABC" && txtpwd.Text == "123") 
Response.Redirect("Registration.aspx"); 
else 
Label1.Text = "Enter Invalid Information"; 
} protected void btnreset_Click(object sender, EventArgs e) 
{ txtname.Text = ""; txtpwd.Text = ""; txtcnfpwd.Text = ""; 
} 
} 
} 
 
 
Registration.aspx Design: 
  
 
Registration.aspx.cs (Code behind): 
using System; 
using System.Collections.Generic; 
using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
namespace validation 
{ public partial class Registration : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
} protected void btnreg_Click(object sender, EventArgs e) 
{ string g, c = " "; string[] a = new string[4]; 
if (RadioButton1.Checked == true) g = RadioButton1.Text; 
else g = RadioButton2.Text; 
if (DropDownList1.SelectedValue == "Arts") c = "10,000"; 
else if (DropDownList1.SelectedValue == "Science") c = "20,000"; 
else if (DropDownList1.SelectedValue == "Commerce") c = "45,000"; 
Response.Redirect("Receipt.aspx?Name=" + TextBox1.Text + "&Gender=" + g + "&Email=" + 
TextBox2.Text + "&Course=" + DropDownList1.SelectedValue + "&Fees=" + c); 
} 
} 
} 
 
 
CourseDetails.aspx Design: 
  
 
CourseDetails.aspx.cs (Code behind): 
using System; 
using System.Collections.Generic; 
using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
namespace validation 
{ 
public partial class CourseDetails : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
 
} protected void Button1_Click(object sender, EventArgs e) 
{ 
Response.Redirect("Home.aspx"); } 
} 
} 
 
 
Receipt.aspx Design: 
  
 
Receipt.aspx.cs (Code behind): using System; 
using System.Collections.Generic; 
using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
namespace validation 
{ public partial class Receipt : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ lblName.Text = Request.QueryString["Name"]; lblGender.Text = Request.QueryString["Gender"]; lblEmail.Text = Request.QueryString["Email"]; lblCourse.Text = Request.QueryString["Course"]; lblFee.Text = Request.QueryString["Fees"]; 
} 
} 
} 
 
 
  
Outputs :- 
 
 
 
 
  
 
3b) Aim :- Create a simple application to demonstrate your vacation using calendar control. 
 
CalendarCtrl.aspx Design: 
  
 
CalendarCtrl.aspx.cs (Code behind): 
using System; 
using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
namespace calendar 
{ public partial class CalendarCtrl : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
 
} protected void Calendar1_DayRender(object sender, DayRenderEventArgs e) 
{ if(e.Day.Date.Day == 5 && e.Day.Date.Month == 9) 
{ 
e.Cell.BackColor = System.Drawing.Color.Yellow; 
Label lb1 = new Label(); 
lb1.Text = "<br>Teachers Day!"; 
e.Cell.Controls.Add(lb1); Image g1 = new Image(); g1.ImageUrl = "td.jpg"; g1.Height = 25; g1.Width = 25; 
e.Cell.Controls.Add(g1); } 
if(e.Day.Date.Day == 7 && e.Day.Date.Month == 9) 
{ 
e.Cell.BackColor = System.Drawing.Color.Yellow; 
Calendar1.SelectedDate = new DateTime(2024, 9, 7); 
Calendar1.SelectedDates.SelectRange(Calendar1.SelectedDate, 
Calendar1.SelectedDate.AddDays(10)); Label lbl1 = new Label(); lbl1.Text = "<br>Ganpati!"; 
e.Cell.Controls.Add(lbl1); Image p1 = new Image(); p1.ImageUrl = "gapati.jfif"; p1.Height = 25; 
p1.Width = 25; 
e.Cell.Controls.Add(p1); 
} 
} protected void btnResult_Click(object sender, EventArgs e) 
{ 
Calendar1.Caption = "SAMBARE"; 
Calendar1.FirstDayOfWeek = FirstDayOfWeek.Sunday; 
Calendar1.NextPrevFormat = NextPrevFormat.ShortMonth; 
Calendar1.TitleFormat = TitleFormat.Month; 
Label2.Text = Calendar1.TodaysDate.ToShortDateString(); Label3.Text = "9-7-2024"; 
TimeSpan d = new DateTime(2024, 9, 7) - DateTime.Now; 
Label4.Text = d.Days.ToString(); 
TimeSpan d1 = new DateTime(2024, 12, 31) - DateTime.Now; 
Label5.Text = d1.Days.ToString(); 
if (Calendar1.SelectedDate.ToShortDateString() == "9-7-2024") 
Label3.Text = "<b>Ganpati Festival Start</b>"; if (Calendar1.SelectedDate.ToShortDateString() == "9-17-2024") 
Label3.Text = "<b>Ganpati Festival End</b>"; 
} protected void btnReset_Click(object sender, EventArgs e) 
{ 
Label1.Text = ""; Label2.Text = ""; 
Label3.Text = ""; 
Label4.Text = ""; 
Label5.Text = ""; 
Calendar1.SelectedDates.Clear(); 
} protected void Calendar1_SelectionChanged(object sender, EventArgs e) 
{ 
Label1.Text = Calendar1.SelectedDate.ToString(); } 
} } 
Output :- 
 
 
3c) Aim :- Demonstrate the use of Treeview operations on the web form. 
 
WebForm.aspx 
Design: 
  
 
Adding nodes & its properties: 
 
 
WebForm.aspx 
 
 
 
 
Output :- 
 
 
 
3d) Aim :- Demonstrate the use of DataList operations on the web form. 
 
WebForm.aspx 
 
 
 
XMLFile.xml 
<?xml version="1.0" encoding="utf-8" ?> < Studentdetail> 
<student> 
<sid>1</sid> 
< sname>Abhishek</sname> 
<sclass>TYIT</sclass> 
</student> <student> 
<sid>2</sid> 
<sname>Sonam</sname> 
<sclass>TYIT</sclass> 
</student> <student> 
<sid>3</sid> 
< sname>Namita</sname> 
< sclass>TYIT</sclass> 
< /student> < student> 
< sid>4</sid> 
< sname>Niraj</sname> 
< sclass>TYIT</sclass> 
< /student> < student> 
<sid>5</sid> 
< sname>Shruti</sname> 
< sclass>TYIT</sclass> 
< /student> 
< /Studentdetail> 
 
 
WebForm.aspx.cs using System; 
using System.Data; using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace 
WebApplication6 
{ public partial class WebForm2 : System.Web.UI.Page 
{ 
protected void Page_Load(object sender, EventArgs e) 
{ if (!IsPostBack) 
{ 
BindData(); 
} 
} protected void BindData() 
{ 
DataSet ds = new DataSet(); ds.ReadXml(Server.MapPath("XMLFile2.xml")); if (ds != null && ds.HasChanges()) 
 
{ 
 	DataList1.DataSource = ds; 
 	DataList1.DataBind(); } 	 
 else  
{ 	 
 	 
DataList1.DataBind(); 
} 
} 
} 
} 
 
  
Output :- 
 
 
 
 
Practical no. 04 
 
4a) Aim :- Create Web Form to demonstrate use of Adrotator Control. 
 
ad.aspx Design: 
  
 
addrotator.xml 
<?xml version="1.0" encoding="utf-8" ?> 
<Advertisements> 
<Ad> 
<ImageUrl>rose.jfif</ImageUrl> 
<NavigateUrl>https://www.1800flowers.com</NavigateUrl> 
<AlternateText> 
Order flowers, roses, gifts and more 
</AlternateText> 
<Impressions>20</Impressions> 
<Keyword>flowers</Keyword> 
</Ad> 
<Ad> 
<ImageUrl>lotus.jfif</ImageUrl> 
<NavigateUrl>https://www.flowerzila.com</NavigateUrl> 
<AlternateText> 
Order flowers, roses and more 
</AlternateText> 
<Impressions>20</Impressions> 
<Keyword>russia</Keyword> 
</Ad> 
<Ad> 
<ImageUrl>lily.jfif</ImageUrl> 
<NavigateUrl>https://poki.com</NavigateUrl> 
<AlternateText> 
Order flowers, roses and more 
</AlternateText> 
<Impressions>20</Impressions> 
<Keyword>russia</Keyword> 
</Ad> 
<Ad> 
<ImageUrl>peri.jfif</ImageUrl> 
<NavigateUrl>https://www.swiggy.com</NavigateUrl> 
<AlternateText> 
Order flowers, roses and more 
</AlternateText> 
<Impressions>20</Impressions> 
<Keyword>russia</Keyword> 
</Ad> 
<Ad> 
<ImageUrl>sunflower.jfif</ImageUrl> 
<NavigateUrl>https://www.easemytrip.com</NavigateUrl> 
<AlternateText> 
Order flowers, roses and more 
</AlternateText> 
<Impressions>20</Impressions> 
<Keyword>russia</Keyword> 
</Ad> 
</Advertisements> 
 
Output :- 
 
 
 
4b) Aim :- Create Web Form to demonstrate use User Controls 
 
MyUersControl.aspx (Run this): Design: 
  
 
WebUserControl1.ascx (User Control): Design: 
  
 
WebUserControl1.ascx.cs (Code behind): 
using System; 
using System.Collections.Generic; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace UserControl 
{ public partial class WebUserControl1 : System.Web.UI.UserControl 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
 
} 
protected void txtBtn_Click(object sender, EventArgs e) 
{ 
Label1.Text = "Your Name is " + txtName.Text + " and you are from " + txtCity.Text; 
} 
} 
} 
 
 
  
Output :- 
 
  
 
Practical no. 05 
 
5a) Aim :- Create a web application to demonstrate the use of session 
 
session1.aspx Design: 
  
 
session1.aspx.cs (Code behind): using System; using System.Collections.Generic; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace session 
{ 
public partial class session1 : System.Web.UI.Page 
{ 
protected void Page_Load(object sender, EventArgs e) 
{ 
 
 
} 
protected void getbtn_Click(object sender, EventArgs e) 
{ 
Session["name"] = name.Text; 
Session["city"] = city.Text; 
Response.Redirect("next.aspx"); 
} 
} 
} 
next.aspx Design: 
  
 
next.aspx.cs (Code behind): using System; 
using System.Collections.Generic; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace session 
{ public partial class next : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
 
} 
protected void Button1_Click(object sender, EventArgs e) 
{ lblname.Text = Session["name"].ToString(); 
lblcity.Text = Session["city"].ToString(); } 
} } 
 
Output :- 
 
  
 
Practical no. 06 
6a) Aim :- Multiline Textbox for Query Processing. 
dbo.Student 
 
 
WebForm.aspx 
  
 
Connecting to Sql Database 
  
 
Testing Connection 
  
 
WebForm.aspx.cs using System; using System.Data.SqlClient; using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace WebApplication2 
{ public partial class WebForm2 : System.Web.UI.Page 
{ 
protected void Page_Load(object sender, EventArgs e) 
{ } 
protected void Button1_Click(object sender, EventArgs e) 
{ 
SqlConnection conn = new SqlConnection("Data Source=.;Initial Catalog=college;Integrated Security=True"); conn.Open(); 
SqlCommand cmd = new SqlCommand(TextBox1.Text, conn); 
SqlDataReader dr = cmd.ExecuteReader(); 
ListBox1.Items.Clear(); 
while (dr.Read()) 
 
{ 
for (int i = 0; i <= dr.FieldCount - 1; i++) 
{ 
ListBox1.Items.Add(dr[i].ToString()); } 
} 
} 
} 
} 
 
 
 
 
 
 
Output :- 
 
 
 
 
6b) Aim :- Displaying record from Database. 
 
dbo.Table_1 
 
 
Webform.aspx 
  
 
Webform.aspx.cs using System; using 
System.Collections.Generic; using 
System.Data.SqlClient; 
 
using System.Linq; using System.Web; using System.Web.UI; 
using System.Web.UI.WebControls; 
 
namespace WebApplication10 
{ 
public partial class WebForm2 : System.Web.UI.Page { 
 protected void Page_Load( object sender, EventArgs e) 
 
{ 
 
} protected void Button1_Click( object sender, EventArgs e) 
{ 
SqlConnection conn = new SqlConnection( "Data Source=.;Initial 
Catalog=College;Integrated Security=True" ) ; conn.Open(); 
SqlCommand cmd = new SqlCommand( "select city,state from Table_1",conn); 
SqlDataReader dr = cmd.ExecuteReader(); 
while( dr.Read()) 
{ 
Label1.Text += dr[ "city" ] .ToString() + " " + dr[ "state" ] 
.ToString() + "<br>" ; 
} dr.Close(); 
conn.Close(); 
} 
} 
} 
 
 
 
 
Output :- 
 
 
 
 
Practical no. 07 
7a) Aim :- Demonstrate use of Datalist link control. 
WebForm.aspx 
  
 
Connecting Datalist to Sql Database 
  
Testing Connection 
  
 
Saving Connection 
  
Selecting Table 
  
 
Testing Query 
  
WebForm.aspx 
  
 
 
 
Output :- 
 
 
 
7b) Aim :- Displaying phone number, author name using author name. 
 
dbo.Student1 
 
 
Webform.aspx 
  
Connecting to Sql Database 
  
 
Testing Connection 
  
 
Webform.aspx.cs using System; 
using System.Collections.Generic; usingSystem.Data; using System.Data.SqlClient; using System.Linq; 
using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace WebApplication3 
{ public partial class WebForm3 : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
SqlConnection conString = new SqlConnection("Data 
Source=DESKTOP-V2K2VGF;Initial Catalog=college;Integrated Security=True"); 
conString.Open(); 
SqlCommand cmdQuery = new SqlCommand("Select * from student1",conString); 
SqlDataAdapter sda = new SqlDataAdapter(cmdQuery); DataSet dsData = new DataSet(); sda.Fill(dsData); 
DropDownList1.DataSource = dsData; 
DropDownList1.DataTextField = "name"; 
DropDownList1.DataValueField = "Phone"; 
DropDownList1.DataBind(); 
} protected void Button1_Click(object sender, EventArgs e) 
{ 
Label1.Text = "You have Selected " + DropDownList1.SelectedValue; 
} 
} 
} 
Output :- 
  
  
Practical no. 08 
 
8a) Aim :- Create a web application to demonstrate use of GridView 
 
dbo.student2 
  
 
WebForm.aspx 
  

Saving Connection 
  
 
Selecting Table 
  
 
Testing Query 
  
 
WebForm.aspx.cs 
using System; 
using System.Collections.Generic; using System.Data.SqlClient; using System.Linq; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; 
namespace WebApplication4 
{ public partial class WebForm1 : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) { } 
protected void Button1_Click(object sender, EventArgs e) 
{ 
SqlConnection conn = new SqlConnection("Data 
Source=DESKTOP-V2K2VGF;Initial Catalog=college;Integrated Security=True"); 
conn.Open(); 
SqlCommand cmd = new SqlCommand("update student1 set name = 
@name, city = @city, phone = @phone where id = @id", conn); 
cmd.Parameters.AddWithValue("@id",TextBox1.Text); cmd.Parameters.AddWithValue("@name",TextBox2.Text); cmd.Parameters.AddWithValue("@city",TextBox3.Text); cmd.Parameters.AddWithValue("@phone", TextBox4.Text); cmd.ExecuteNonQuery(); 
} protected void Button2_Click(object sender, EventArgs e) 
{ 
SqlConnection conn = new SqlConnection("Data 
Source=DESKTOP-V2K2VGF;Initial Catalog=college;Integrated Security=True"); 
conn.Open(); 
SqlCommand cmd = new SqlCommand("insert into student1 values(@id, 
@name, @city, @phone)", conn); 
cmd.Parameters.AddWithValue("@id", TextBox1.Text); cmd.Parameters.AddWithValue("@name", TextBox2.Text); cmd.Parameters.AddWithValue("@city", TextBox3.Text); cmd.Parameters.AddWithValue("@phone", TextBox4.Text); cmd.ExecuteNonQuery(); 
Label1.Text = "entry successful."; conn.Close(); } protected void Button3_Click(object sender, EventArgs e) 
{ 
TextBox1.Text = ""; TextBox2.Text = ""; 
TextBox3.Text = ""; 
TextBox4.Text = ""; 
} protected void Button4_Click(object sender, EventArgs e) 
{ 
SqlConnection conn = new SqlConnection("Data 
Source=DESKTOP-V2K2VGF;Initial Catalog=college;Integrated Security=True"); 
conn.Open(); 
SqlCommand cmd = new SqlCommand("delete from student1 where id=@id", conn); cmd.Parameters.AddWithValue("@id",TextBox1.Text); cmd.ExecuteNonQuery(); 
Label1.Text = "deletion successful."; conn.Close(); 
} protected void SqlDataSource1_Selecting(object sender, SqlDataSourceSelectingEventArgs e) 
{ 
} 
protected void GridView1_SelectedIndexChanged(object sender, EventArgs e) 
{ 
TextBox1.Text = GridView1.SelectedRow.Cells[1].Text; TextBox2.Text = GridView1.SelectedRow.Cells[2].Text; 
TextBox3.Text = GridView1.SelectedRow.Cells[3].Text; 
TextBox4.Text = GridView1.SelectedRow.Cells[4].Text; 
} 
} 
} 
 
 
 
 
 
 
Output :- 
 
 
 
Practical no. 09  
9a) Aim :- Create a web application to demonstrate use of various Ajax controls. 
 
WebForm11.aspx 
  
 
WebForm11.aspx.cs 
using System; using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; usingSystem.Web.UI.WebControls; 
namespace WebApplication6 
{ public partial class WebForm11 : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
} protected void Button1_Click(object sender, EventArgs e) 
{ 
Label1.Text = System.DateTime.Now.ToString(); 
} 
} 
} 
 
 
Output :- 
 
 
 
 
 
 
 
 
 
 
 
WebForm12.aspx 
  
 
 
WebForm12.aspx.cs 
using System; 
using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; namespace WebApplication6 
{ public partial class WebForm12 : System.Web.UI.Page 
{ protected void Page_Load(object sender, EventArgs e) 
{ 
} protected void Timer1_Tick(object sender, EventArgs e) 
{ 
Label1.Text = System.DateTime.Now.ToString(); 
} 
} 
} 
 
 
 
 
 
 
Output :- 
 
  
 
Practical no. 10 
 
10a) Aim :- Create a web application to demonstrate JS Bootstrap Button. 
 
boot.aspx 
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="boot.aspx.cs" 
Inherits="bootstrap.boot" %> 
<!DOCTYPE html> 
<html xmlns="http://www.w3.org/1999/xhtml"> 
<head runat="server"> 
<title></title> 
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js"> 
</script> 
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitterbootstrap/3.0.3/css/bootstrap.min.css" media="screen" /> 
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/twitterbootstrap/3.0.3/js/bootstrap.min.js"> </script> 
</head> 
<body> 
<button type="button" class="btn btn-info btn-lg" data-toggle="modal" data-target="#myModal">Open 
Modal</button> 
<div id="myModal" class="modal fade" role="dialog"> 
<div class="modal-dialog"> 
<div class="modal-content"> 
<div class="modal-header"> 
<button type="button" class="close" data-dismiss="modal">&times;</button> 
<h4 class="modal-title">Hi this is my first modal</h4> 
</div> 
<div class="modal-body"> 
<p>Bootstrap is the Best...!</p> 
</div> 
<div class="modal-footer"> 
<button type="button" class="btn btn-default" data-dismiss="modal">Close</button> 
</div> 
</div> 
</div> 
</div> 
</body> 
</html> 
 
 

 
 
 
 
 
 
 
 
 
 
 

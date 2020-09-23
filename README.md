<div align="center">

## Send an E\-mail from VB\.NET


</div>

### Description

Here is a code to send an e-mail from a Winform made in VB.NET. Check it!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Robson Mendonça](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/robson-mendon-a.md)
**Level**          |Intermediate
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |VB\.NET
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__10-9.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/robson-mendon-a-send-an-e-mail-from-vb-net__10-368/archive/master.zip)





### Source Code

<br>
To send an e-mail in VB.NET, we can use the System.Web.Mail class. See the code below:<br>
<br>
<br>
Imports System.Web.Mail<br>
<br>
Public Class WebForm1<br>
Inherits System.Web.UI.Page<br>
Protected WithEvents Label1 As System.Web.UI.WebControls.Label<br>
Protected WithEvents TextBox1 As System.Web.UI.WebControls.TextBox<br>
Protected WithEvents Label2 As System.Web.UI.WebControls.Label<br>
Protected WithEvents TextBox2 As System.Web.UI.WebControls.TextBox<br>
Protected WithEvents Label3 As System.Web.UI.WebControls.Label<br>
Protected WithEvents TextBox3 As System.Web.UI.WebControls.TextBox<br>
Protected WithEvents Label4 As System.Web.UI.WebControls.Label<br>
Protected WithEvents TextBox4 As System.Web.UI.WebControls.TextBox<br>
Protected WithEvents RadioButton2 As System.Web.UI.WebControls.RadioButton<br>
Protected WithEvents RadioButton1 As System.Web.UI.WebControls.RadioButton<br>
Protected WithEvents Button1 As System.Web.UI.WebControls.Button<br>
<br>
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click<br>
If RadioButton1.Checked Then<br>
 Dim simplemail As New MailMessage()<br>
 Dim from_, to_, title_, message_ As String<br>
 from_ = TextBox1.Text.ToLower.Trim()<br>
 to_ = TextBox2.Text.ToLower.Trim()<br>
 title_ = TextBox3.Text.Trim()<br>
 message_ = TextBox4.Text.Trim()<br>
 SmtpMail.Send(from_, to_, title_, message_)<br>
Else<br>
 Dim AttachEmail As New MailMessage()<br>
 With AttachEmail <br>
  .From = TextBox1.Text.ToLower.Trim<br>
  .To = TextBox2.Text.ToLower.Trim<br>
  .Subject = TextBox3.Text.Trim<br>
  .Body = "<HTML><Body>" & TextBox4.Text.Trim() & "</body></html>"<br>
  .BodyFormat = MailFormat.Html<br>
  .Priority = MailPriority.High<br>
  .Attachments.Add(new MailAttachment("c:\attach.txt"))<br>
 End With<br>
 SmtpMail.Send(AttachEmail)<br>
End If<br>
End Sub<br>
End Class<br>
<br>


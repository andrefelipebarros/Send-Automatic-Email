<div align=center>

<h1>📩 SEND EMAILS 🐍</h1>
I will teach you in an easy way, to send emails using Python with a scheduled time.
</div>

<h2>📝Instructions</h2>

<!-- FIRST STEP IS HERE -->

<details>
<summary><strong>🔸First Step</strong></summary>

<p></p>
<p>example:</p>

```sh
  #import libraries with command: "pip install" and write the name of the librarie(smtplib and schedule).
import os
import smtplib 
from email.message import EmailMessage
import schedule

#Adding your Email (Google: "gmail")

email = "youremail@gmail.com"
     
```
</details>

<!-- SECOND STEP IS HERE -->

<details>
<summary><strong>🔹Second Step</strong></summary>

<p></p>

```sh
  '''here, you will visit your google and make the following settings:
1-Enable two-factor option.
2- Visit: https://myaccount.google.com/apppasswords
3- Generate password with google email category.
4- put password in a notepad file.'''

with open('senha.txt') as f: #upload previously developed notepad file
    senha = f.readlines() #Consult file 
    
    f.close() #Stop Consult File
    
senha_do_email = senha[0]

senha_do_email

#Email Informations

msg = EmailMessage()
msg['Subject']  = 'Enviando e-mail com Python'
msg['From'] = 'seuemail@gmail.com'
msg['To'] = 'qualquercoisa@gmail.com'
msg.set_content("Segue o relatório diário")

```
</details>

<!-- THIRD STEP IS HERE -->

<details>
<summary><strong>🔻Third Step</strong></summary>

```sh
  
#Example of attaching file

with open('minecraft.pdf', 'rb') as content_file:
    content = content_file.read()
    msg.add_attachment(content, maintype='application', subtype='pdf', filename='minecraft.pdf')
    
    
#Sending Email

with smtplib.SMTP_SSL('smtp.gmail.com', 465) as smtp:
    
    smtp.login(email, senha_do_email)
    smtp.send_message(msg)
```
</details>

<!-- suggestion -->

<details>
<summary><strong>⚠️Suggestion</strong></summary>

<h2>I suggest you go to my profile and see the repository:</h2> 
["https://github.com/andrefelipebarros/Automacao-Scripts-Python/"]

```sh
  
#Now Add the codes in a "def" and create a time with schedule tasks

schedule.every().hours.at("06:00").do('''Your-Def-Name''') #enter the codes on the Clock at 6:00 am

while 1:
    schedule.run_pending() #Play in the schedule
```
</details>


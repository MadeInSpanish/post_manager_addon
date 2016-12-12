# Send Email With Markdown File

> This google add on sends a markdown file to people who are on the collaborators list

[![Post Manager Add-on](https://raw.githubusercontent.com/MadeInSpanish/post_manager_addon/master/img/video.png)](https://www.youtube.com/watch?v=koz8c1ZW_o4 "Click to Watch!")

## Usage

1. Open Google Docs and the add-on should be available from the `Add-ons` menu.
2. You will need to accept the authorization request.
3. After a moment the users of the document should receive an email with the Markdown file.

## Credits

[gdocs2md](https://github.com/mangini/gdocs2md) Google App Script was originally created by Renato Mangini.

## Info
If you prefer to save the file in your google drive you only have to copy this code


```
var resname = DocumentApp.getActiveDocument().getName();
var resdoc = DocumentApp.create("Markdown_"+resname+".md");
var resbody = resdoc.getBody();
resbody.setText(text);
```

and remove this
```
attachments.push({"fileName":DocumentApp.getActiveDocument().getName()+".md", "mimeType": "text/plain", "content": text});

MailApp.sendEmail({
  to: recipientsTO,
  subject: subject,
  htmlBody: message,
  attachments: attachments
});
```

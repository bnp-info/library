### Purpose

This is my link library where I can store references to online sites, articles and other resources.

### Automated Issue Handling

To facilitate the frequant additions of new posts, I have added two GitHub Actions workflows to the project. The first processes the Issue and writes a new post in the staging branch based on it's contents when the Issue is moved to the closed state. The second evaluates all image files in the asstes/images directory in the staging branch and resizes anything over 800 pixels wide down to that width and 90% quality to make them more web-friendly. In theory, it should not matter in the issues are processed first or the images resized first, as long as all necessary changes are made before creating a pull request from staging to master. Just be aware that images uploaded for which the corresponding Issue isn't processed will (a) be resized, (b) retain their original names, and (c) will be published even though no post will refer to them.

### Procedures

For _each_ new post:
1. Create a new Issue using the Library Post template. Fill all fields and save.
2. Upload a screenshot for the post's header to the assets/images directory.
3. Add the name of the uploaded image (e.g. IMG_0123.jpeg) to the Image field of the Issue.

When ready to _batch_ post to the web:
1. Run the image-resizing workflow manually.
2. Move each Issue to the closed state to generate the post files.
3. Create and execute a pull request from staging to master (this regenerates the whole static site).

### Copyright

Copyright (C) 2025 Brandon's Notepad

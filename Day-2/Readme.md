## Day - 2 of #30DaysofBackend

# Version Control System

# Introduction

As a Software Developer, I see people name their some local code files, jupyter notebooks or even documents like resume have file names like these:

- fibonacci.py
- fibonacci_updated.py
- fibonacci_updated_latest.py
- resume_2019.doc
- resume_updated.doc

I see lot of people do that and even I do that. There is nothing wrong in doing that way, this is the reason why we have "Save As" button. That button lets us updated the file and save it separately with out overriding existing one.

Coming to software development is it a good practice? No, because this makes the file system more complicated and lot of files to take care of.

But, why in the first place we are doing it? Because we want to update the content of the file and also secure the old file because that gives us previlege to go back and use it when needed. 

Also, what if you want to work with you friends or teammates on something together may be something like creating a marketing flyer. For this people might be coming with different ideas and there will also be versions for that. How to maintain this team collabaration of working on a single file, one solution might be "shared folder"

# Version Control System:

VCS offers us lot of features addressing the above problems. Do you think that if windows updgrades it OS the updated version is stored like this "Windows-11_Updated_Latest.iso"? No, right. So, a good VCS should do the following:

1. Backup and Restore: Saved the files after edited. Now if you want to access the file as it was on Jul 16th 1997, you can get it.

2. Synchronization: People share files and you will have everything that they share with latest version.

3. Short-term Undo: Messed up a file? You can go back to previous version of that file when it is working good.

4. Long-term Undo: Facing a bug that was due to a code change done a year back? We can go back to that file too.

5. Track Changes: As you work on file and you update them, we can assign a message to each change that helps us in tracking the changes based on the message, answering questions like Why we did this change?

6. Track Ownership: VCS tags every change with the name of the person who made it.

7. Sandboxing: Working on a big feature? Not sure if that will mess up the existing code base? This helps us work on the feature in isolated space, test it and then checking in back to the main code base.

8. Branching and Merging: This is similar to sandboxing where you can work on features in isolated environment but this also provide tracking the changes


## Actions:

- Add: Adds the file into repository

- Revision: Revisions for each file when changed

- Head: Points to latest revision of the project

- Check out: Downloads the file from repository to local

  ![image-1](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/84c1bdc4-fbd6-45d0-bb32-a7873608216f)


- Check in: Adds the latest change of the file to repository

    ![image](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/c842cbea-a3d9-4d54-ba26-127fdef6bb55)


- Check in message: Short message describing what has changed

- Revert: Throw away local changes and go back to latest version in repository

- diff: Shows the differences between two revisions

  ![image-2](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/ed9bed6d-99ef-4f30-b0a9-77747e677730)

- branch: Creates an isolated environment from the project.

  ![image-3](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/0cb0c8f9-53f0-4e51-984d-b62080c1fffe)

- merge: merges the changes made in the isolated environment to the working repository files.

  ![image-4](https://github.com/nehruperumalla/30DaysofBackend/assets/41884444/82d834de-654c-4f3c-9796-cac674722569)


# References:

https://betterexplained.com/articles/a-visual-guide-to-version-control/

https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control

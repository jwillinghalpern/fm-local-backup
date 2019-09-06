# fm-local-backup

## Local Backup

Local backup module for working on non-hosted FileMaker files. Create local backup of multiple files with one script. The main file tells each configured file to "Save a Copy As..."

![Backup Demo](fm-local-backup-short.gif)

## REQUIREMENTS
  
- Filemaker Pro Advanced 17+

## INSTALLATION / CONFIGURATION

1. Copy the "Local Backup" folder into your main "dispatch" file's "Modules" folder.
   - This dispatch file will need external data source references to the other files in your project.
2. Paste the `Local Backup: All Files` script folder into each file that you want to backup.
   - You can also paste the whole module in if you want, but pasting only the `All Files` folder helps clarify your intention
3. In the dispatch file, in the script `Local Backup: Run`, add a Perform Script[] script step for each external data source file you
want to backup.
   - The step for each file should look like this: `Perform Script [ “Local Backup: Backup This File ( folder )” from file: "<<YOUR FILE NAME>>”; Parameter: $param ]`
4. (Optional) Adjust the `Local Backup: Config` script as desired.

## NOTES

- If your files were created with FileMaker 18+, or if you manually restricted File Access protection in Manage > Security, then the first time you run the backup script, you'll be prompted to allow access for each file that has this enabled.

## HISTORY

### 1.0.0

- 2019-09-05    Josh Willing
- Initial release

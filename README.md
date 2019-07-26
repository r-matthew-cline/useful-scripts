# Useful Scripts

This repo contains useful scripts that I wanted to save and instructions on
how to use them.

## src2pdf

This script will recursively convert all source code files in a directory to
a pdf file with a table of contents.

### Dependencies

- texlive-latex-extra
- latex-xcolor
- texlive-latex-recommended

### Running the Script

The language option needs to be added to the lstdefinestyle options depending
on the language you are trying to convert to a pdf. This creates some 
complications for things like config files being included, but it is still 
pretty useful.

```bash
./src2pdf
```

### Credits

This script was originally found on StackExchange from author terdon. The 
original post can be found [here](https://superuser.com/questions/601198/how-can-i-automatically-convert-all-source-code-files-in-a-folder-recursively/601412)

## aws-mfa

This script will fetch a session token from AWS and populate a profile for
the awscli, so that users on an instance with an instance role attached
can use an IAM user's credentials to run commands.

### Dependencies

- awscli
- two profiles in $HOME/.aws/config and $HOME/.aws/credentials, the .aws directory in this repo shows examples of what those profiles need in them

### Running the Script

The profile that will be populated with the session token information needs to be
passed as the first argument, and the profile with the access token of the IAM user
needs to be passed as the second argument. The interactive session will then prompt the
IAM user for their MFA token. After the script has run the mfa profile will be used
to execute awscli commands that require MFA.

```bash
./aws-mfa.sh debugmfa debug
```

To use the awscli with the update MFA credentials pass the --profile debugmfa flag to 
the commands as follows

```bash
aws s3api put-object --bucket debug-test-bucket --key some_file --body local_file --profile debugmfa
```

### Credits

This script was pulled from a CodeCommit tutorial in AWS's
[documentation](https://aws.amazon.com/blogs/devops/secure-aws-codecommit-with-multi-factor-authentication/)

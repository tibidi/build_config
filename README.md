# Accessing the Build Server
http://jenkins.unlegacy-android.org/

# Authenticating to the Build Server
You must be a member of the Unlegacy-Android organization,
Jenkins will authorize using OAuth to GitHub.

# Using the Build Server
Click the "android" job.
Configure what you want to build.

# Adding or updating a device
Edit build-targets and submit a gerrit change. The syntax for that file
is documented in its first few lines


            checkout poll: false, scm: [$class: 'RepoScm', currentBranch: true, destinationDir: '/unlegacy/'+env.BRANCH, forceSync: true, jobs: 8, manifestBranch: env.BRANCH, manifestRepositoryUrl: 'https://github.com/Unlegacy-Android/android.git', noTags: true, quiet: true]
            checkout poll: false, changelog: false, scm: [$class: 'RepoScm', currentBranch: true, depth: 1, destinationDir: '/unlegacy/'+env.BRANCH, forceSync: true, jobs: 8, manifestBranch: env.BRANCH, manifestRepositoryUrl: 'https://github.com/Unlegacy-Android/android.git', noTags: true, quiet: true, showAllChanges: true, resetFirst: false, trace: false]
       

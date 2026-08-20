# Practice 0

Welcome to CS445/545. In this class, we will be using a variety of
tools that will require some initial configuration. 


## Instructions for Hydra
1. Connect to UTK's VPN using Ivanti
1. ssh into hydra, fowarding port 8888: (YOU MUST DO THIS EVERY TIME YOU SSH WHEN USING JUPYTER)
    ```
    ssh -L 8888:localhost:8888 [netID]@hydra[N].eecs.utk.edu
    ```
1. setup aliases for python and pip - add this to your shell init script (.bashrc / .zhsrc / etc):
    ```
    alias python='/usr/bin/python3.11'
    alias pip="/usr/bin/python3.11 -m pip"
    ```
1. source your new init script:
    ```
    source [path/to/init/script]
    ```
1. confirm alias - run `which python` and `which pip`. Should return:
    ```
    python=/usr/bin/python3.11
    ```
    and
    ```
    pip='/usr/bin/python3.11 -m pip'
    ```
1. update pip: run `pip install --upgrade pip`
1. Install jupyter notebook packages:
    ```
    pip install notebook
    ```

## Instructions for Github

1. To start, [**fork** repository][forking] [utk-cs445-fall26/Practice0][assignment]
1. [**Clone**][ref-clone] the repository to a location of your choice
  If you have not set these up, please do (replace USERNAME with your own github username):
    ```
	git config --global user.name USERNAME
	git config --global user.email 'whatever email you are willing to share'
    ```
 
1. You may also want to set up your credentials to be cached (in seconds: 3600=1hour)
    ```
	git config credential.helper 'cache --timeout=3600'
    ```
    
1. Set up your default editor if you don't like vi (vi is set by default)
    ```
    git config --global core.editor nano
    ```
    
1. Now clone
    ```
	git clone https://USERNAME@github.com/USERNAME/Practice0
    ```
 
1. You will be asked to enter your github username and password

1. Hint: to avoid typing GitHub passwords you can add the following to your 
   .ssh/config on the host where you run git commands:
            
         host github
             User USERNANE
             HostName github.com
             IdentitiesOnly yes
             IdentityFile ~/.ssh/id_rsa
         
    Then the git clone will look like:
         ```
          git clone git@github:USERNAME/Practice0
         ```
    You will also need to put your public key on github as described in step 4 of [instructions](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

## Instructions for Assignment
1. Install required packages for Practice0
    ```
    pip install matplotlib scipy pandas numpy bs4 nltk bson pymongo
    ```
1. cd to the directory you cloned Practice0
1. Please change the name of the notebook from Practice0.ipynb to [YOUR NETID].ipynb, so I can merge it in the central repository once you submit your pull request.
      To do so, run the following command: 'mv Practice0.ipynb YourNetID.ipynb'
1. Start the Jupyter Notebook Server (If on Hydar you must SSH with the -L flag as described in the Instructions for Hydra section)
    ```
    python -m notebook
    ```
1. Open the http://localhost:8888 link in your browser
1. Edit/Run the example in the browser and do requested tasks to complete the assignment
1. Once finished with the assignment, run File -> Save Notebook and [**commit**][ref-commit] changes to complete your solution.

        git add YourNetID.ipynb
        git commit -m '<your commit comment>'

1. Now back in the shell [**Push**][ref-push]/sync the changes to github.

        git push origin master
   
1. At https://github.com/USERNAME/Practice0
   Create a [**pull request**][pull-request] on the
   original repository [utk-cs445-fall26/Practice0][assignment]  to
   turn in the assignment.


[assignment]: https://github.com/utk-cs445-fall26/Practice0
[forking]: https://guides.github.com/activities/forking/
[ref-clone]: http://gitref.org/creating/#clone
[ref-commit]: http://gitref.org/basic/#commit
[ref-push]: http://gitref.org/remotes/#push
[pull-request]: https://help.github.com/articles/creating-a-pull-request

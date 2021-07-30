<p align="center" style="background-color:"><img src="https://www.theworkspace.co.za/wp-content/uploads/2020/10/Sambe-Consulting-logo-800x600.png"  width="400"></p>

<p align="center"><h2 style="color: #193967; text-align: center">
    Build a REST API
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

#### Introduction 
In this exercise we are going to build a REST API that tells a jokes every time this endpoint `/tell` is requested. And learns a new joke when the joke is 
posted to this endpoint. `/learn`. Using Sego.

So I suspected that some of you are being lazy with the resources that I provided and are not taking full advantage fo their usefulness.
So today i gamified my lesson. I provided the full solution as promised but you had to do some reading first. Only those who have done some studying will get to this solution.
I ask if you have discovered this do not share it with your colleagues this is a teaching moment.Lets begin.

###Environment
1. linux machine 
2. Python 3.xx 
3. Pycharm 

#####Step one install Sego CLI: 
1. Visit https://github.com/sambe-consulting/sego-cli
   -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/sego-cli-repo.png"/>
2. Click Releases you will be redirected to the release page 
  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/releases.png"/>
3. Open your terminal and type `mkdir ~/rest && cd ~/rest`
4. Under Release v5 Assets click the icon labelled "sego" with the cube close to it, that will open a download dialog, navigate to 
`/home/<user-name>/rest` then download the binary in that directory.
   
5. Go to your terminal and type `sudo chmod +x sego` this makes the binary executable 
6. then type `sudo mv sego /usr/local/bin/sego` this moves the binary to a system wide bin directory. 

#####Step two test Sego CLI: 
1. type `sego`, note for the first time you running a `sego` command it will take a while because it has to go through the ``automatic`` installation process. 
2. After the installation process is done you will see this screen :
  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/sego-command.png"/>
   
3. you can press CTRL+Z to exit the above screen 

##### set three create an application 
1. type `sego application generate` press ENTER 
2. Fill in the form: 
  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/form.png"/>
3. type `cd joker` to move inside the app 
4. type ` source joker_env/bin/activate` to activate the app's environment   
5. type `pip install -r requirements.txt ` to install all requirements 
6. type `python -m gunicorn main:app  ` to start the application if you get a port collision use `sudo fuser -k 8000/tcp` the try again 
7. if everything went well you will have: 
  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/started.png"/>
   
8. Go to your browser then type http://127.0.0.1:8000 in the address bar, congratulation you have created your first Sego App 
  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/mainscreen.png"/>
   

##### Step four create a controller: 
1. Go to pycharm 
2. Click on `file -> open ` 
3. Navigate to where you have stored joker `/home/<username>/rest/joker` my path looks like this `/home/kabelo/rest/joker`
4. Open he directory you will see this file structure in your pycharm file explorer :

  -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/struct.png"/>

5. By navigating to controllers you will see the HomeController inside the file there is this code: 

```python   


# ************************************************************************#
# Title:                    Home Controller                               #
# Description:              This class houses all actions related to      #
#                           the homepage                                  #
# Author:                   Sambe Consulting <development@sambe.co.za>    #
# Original Date:            23 March 2021                                 #
# Version:                  0.1.0                                         #
# ************************************************************************#

from . import BaseController


class HomeController(BaseController):

    def index(self, request, response):
        response.html = self.Views.render_view("home.html")

```

6. Pay attention to the method named index which returns "renders" a "view" called home.html
7. Next navigate to `routes` directory  and then open the file called `web_routes.py ` read through the EXAMPLE route with 
 - route_name = "homepage" 
 - http_method = Verb.HTTP_GET  
 - controller = "HomeController"  note  that this is the home controller we check above 
 - action = "index"  again this is the same ```python def index(self,request,response):```
 - url = "/" 

What all of this means is that when a user asks for a path `/` Sego will take their request send it to a controller named HomeController, and run an 
action called index. 

8. The `api_routes.py` file does not have any routes defined yet. Let's' start 
9. Define the `/learn` endpoint, open the `api_routes.py` file and write: 

```python

learn_route = Route(name="learn",verb=Verb.HTTP_POST,controller="JokerController",action="learn",url="/learn")
router.add_route(learn_route)

```

10. To Create the `JokerController` we first have to activate our application: 
- list all applications run in the terminal `sego application list`
    -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/listapp.png"/>
  
- activate joker first copy the `application_identifier` for joker ,then run `sego application activate --id=<id>` e.g `sego application activate --id=8a32ab84-a1a4-46fb-833e-9e21bd33def1`
- Now list the applications again using `sego application list` then note that the active column for `joker` will be set to 1 
- After activating an application we can access its internal components like `routes` and `controllers` e.g `sego controller list` will give 
you all controllers for the active applications and their respective actions 
- Now run `sego controller generate` and fill in the form: 
        -<img src="https://raw.githubusercontent.com/sambe-consulting/quick-res/master/controller_form.png"/>
  
11. Navigate to controllers in pycharm you will see a new file named `jokerController` with this code inside: 
```python 

# ************************************************************************#
# Title:                    JokerController                          #
# Description:              Joker controller                    #
# Author:                   kabelo.masemola@sambe.co.za <kabelo.masemola@sambe.co.za>                 #
# Original Date:            30/07/2021 03:59:18                           #
# Version:                  1.0.0                                   #
# ************************************************************************#
from . import BaseController

class JokerController(BaseController):

      def __init__(self):
          pass

      def index(self, request, response):
         response.html = self.Views.render_view("home.html")



```

#####Step five create the /learn endpoint action 

1. inside the JokerController add an action called learn this way: 
```python

# ************************************************************************#
# Title:                    JokerController                          #
# Description:              Joker controller                    #
# Author:                   kabelo.masemola@sambe.co.za <kabelo.masemola@sambe.co.za>                 #
# Original Date:            30/07/2021 03:59:18                           #
# Version:                  1.0.0                                   #
# ************************************************************************#
from . import BaseController
import json,os

class JokerController(BaseController):

      def __init__(self):
          pass

      def index(self, request, response):
         response.html = self.Views.render_view("home.html")

      def learn(self, request, response):
          file_name = "jokes.json"
          req_body = json.loads(request.body.decode('utf-8'))
          print(req_body)
          if not os.path.exists(file_name):
              with open(file_name,"w") as f:
                  f.write(json.dumps({"jokes":[]}))

          with open(file_name,"r") as f:
              jokes = json.loads(f.read())
          jokes["jokes"].append(req_body)

          with open(file_name,"w+") as f:
              f.write(json.dumps(jokes))
          response.json = {"message":"Joke has been stored"}


```
2. To teach the api a  new joke create a file called `joke_file.json` then add a joke definition like this:

```json 
{
    "name":"neutron joke",
    "joke":"A neutron walks into a bar, and asks the bartender how much for a drink, the bartender says :For you no charge"
}

```
3.Then you can post the joke like this in the terminal.
```bash 

curl --data-binary @joke_file.json --header "Content-Type: application/json" -XPOST http://127.0.0.1:8000/learn

```

#####Step six create the /tell endpoint action 

1. Inside the `api_routes.py` file add another route:

```python
tell_route = Route(name="tell",verb=Verb.HTTP_GET
                   ,controller="JokerController",
                   action="tell",url="/tell")
router.add_route(tell_route)

```

2. inside the `JokerController` add the `tell` action:

```python 

# ************************************************************************#
# Title:                    JokerController                          #
# Description:              Joker controller                    #
# Author:                   kabelo.masemola@sambe.co.za <kabelo.masemola@sambe.co.za>                 #
# Original Date:            30/07/2021 03:59:18                           #
# Version:                  1.0.0                                   #
# ************************************************************************#
from . import BaseController
import json,os,random

class JokerController(BaseController):

      def __init__(self):
          pass

      def index(self, request, response):
         response.html = self.Views.render_view("home.html")

      def learn(self, request, response):
          file_name = "jokes.json"
          req_body = json.loads(request.body.decode('utf-8'))
          print(req_body)
          if not os.path.exists(file_name):
              with open(file_name,"w") as f:
                  f.write(json.dumps({"jokes":[]}))

          with open(file_name,"r") as f:
              jokes = json.loads(f.read())
          jokes["jokes"].append(req_body)

          with open(file_name,"w+") as f:
              f.write(json.dumps(jokes))
          response.json = {"message":"Joke has been stored"}

      def tell(self,request,response):
          file_name = "jokes.json"
          with open(file_name,"r") as f:
              jokes = json.loads(f.read())

          joke_count = len(jokes["jokes"])
          joke_to_tell_index = random.randint(0,joke_count-1)
          joke_to_tell = jokes["jokes"][joke_to_tell_index]
          response.json = joke_to_tell


```

3. Go to http://127.0.0.1:8000/tell this will give you a random joke everytime 












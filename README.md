# XQM

XQM is a fully-fledged mobile application for user interaction with media collections on the user’s mobile device. 

The application works with a simple user interface which provides the user with the opportunity to interact with her image collection in an efficient way. 
The app contains two phases, an interactive exploration phase and a data processing phase. 

[App Architecture](F1-architecture.pdf "App Architecture")

In the first phase, XQM gradually builds an interactive classifier capable of fulfilling the user’s information need. This is done by presenting the highest ranked images from the current model in the user interface and asking the user to provide feedback on those, labelling them as relevant or not relevant. The labels are then used to retrain the interactive classifier, and the classifier is in turn used to query the feature database for a new set of suggested images to judge. This interactive process continues until the user is satisfied or decides to start from scratch. 
To support the model construction, the app also has a data processing phase, where state-of-the-art semantic feature extraction is deployed on a dedicated server. This phase takes place on an external Python server, which can be set up on the user’s computer.

When installing the app, existing images on the phone are analysed in this manner to build XQM’s feature database, and subsequently the user can analyse new images to add to the feature database. 

**User interface**
![User interface](screens.png?raw=true "Main Screens")

**Open-source**
XQM is proven to be an efficient tool not only to the experienced users, but also for the novice or casual users unfamiliar with 
interactive learning, with clear potential for further improvement. 


**Set up instructions**

1. Clone repository
2. Download files for the RexNeXt101 model
3. Set up the image analysis 
3.1. Insert your local IP address into ServerClient.java line 36. 
3.2. Insert your local IP address into flask_server.py line 107. 
3.3. Insert the required files into line 41, 45 and 92 (follow comments in code). 3.4. Install torch, torchvision, Pillow and numpy 
3.5. Start the server (before running the app!) with python3 flask_server.py
4. Connect the mobile device and the computer that hosts the server to same wifi network
5. Install the app


**Third party content**

For implementing an interactive classifier, we used the Libsvm library, a simple, easy-to-use, and efficient software for SVM classification and regression.
https://github.com/cjlin1/libsvm

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS,  ``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE REGENTS OR 
CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, 
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 


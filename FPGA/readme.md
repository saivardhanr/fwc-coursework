Install the zip provided i.e. fpga.zip onto Desktop

Open terminal and go to the fpga folder

bash
Copy
Edit
cd ~/Desktop/fpga
Make setup script executable

bash
Copy
Edit
chmod +x setup.sh
This command makes scripts and programs executable without needing to prefix them with ./.

Run the setup script

bash
Copy
Edit
sudo bash setup.sh
After running the above command, do the following:
Go to: File Manager → Other Locations → Computer → root
Copy the folders Symbiflow and Pygmy-dev and paste them into:

bash
Copy
Edit
/home/sai vardhan/Desktop/fpga
Download arch.tar.gz from this link and place it in the same directory:
Download Link

Make sure /home/sai vardhan/Desktop/fpga contains the following:

pygmy-dev

setup.sh

symbiflow

arch.tar.gz

Install Dependencies and Set Environment

bash
Copy
Edit
sudo apt update -y
sudo apt upgrade -y
sudo apt install openssh-server sshpass build-essential libssl-dev libffi-dev python3-dev bison flex git tcl-dev tcl tcl-tclreadline libreadline-dev autoconf libtool make automake texinfo pkg-config libusb-1.0-0 libusb-1.0-0-dev gcc-arm-none-eabi libnewlib-arm-none-eabi telnet python3 apt-utils libxslt-dev cmake curl python3-pip python3-venv -y
pip3 install gdown lxml simplejson
sudo apt install openssh-server sshpass
sudo apt install build-essential libssl-dev libffi-dev python3-dev bison flex git tcl-dev tcl tcl-tclreadline libreadline-dev autoconf libtool make automake texinfo pkg-config libusb-1.0-0 libusb-1.0-0-dev gcc-arm-none-eabi libnewlib-arm-none-eabi telnet python3 apt-utils libxslt-dev python3-lxml python3-simplejson cmake curl python3-setuptools python3-pip
cp arch.tar.gz /home/sai vardhan/Desktop/fpga/arch.tar.gz
export INSTALL_DIR=/home/sai vardhan/Desktop/fpga/symbiflow
tar -C "$INSTALL_DIR" -xvf /home/sai vardhan/Desktop/fpga/arch.tar.gz
export PATH="$INSTALL_DIR/quicklogic-arch-defs/bin:$INSTALL_DIR/quicklogic-arch-defs/bin






You said:
generate in one complete thing


ChatGPT said:
Sure! Here's the complete and unified guide with "nikhil" replaced by "sai vardhan" throughout:

✅ FPGA Installation & Setup Guide (For User: sai vardhan)
🔧 Step-by-step Installation and Execution
Download and Extract Files

Place the provided fpga.zip on your Desktop.

Extract it to get a folder named fpga.

Open Terminal and Navigate to the Folder

bash
Copy
Edit
cd ~/Desktop/fpga
Make the Setup Script Executable

bash
Copy
Edit
chmod +x setup.sh
This makes the script runnable directly without ./.

Run the Setup Script with Superuser Privileges

bash
Copy
Edit
sudo bash setup.sh
Manual File Movement

Go to: File Manager → Other Locations → Computer → root

Copy the folders Symbiflow and Pygmy-dev

Paste them into:

bash
Copy
Edit
/home/sai vardhan/Desktop/fpga
Download arch.tar.gz File

Use the following link:
Download arch.tar.gz

Place the downloaded file in:

bash
Copy
Edit
/home/sai vardhan/Desktop/fpga
Verify /home/sai vardhan/Desktop/fpga Contains:

pygmy-dev

symbiflow

setup.sh

arch.tar.gz

🛠️ Install Dependencies and Set Environment
bash
Copy
Edit
sudo apt update -y
sudo apt upgrade -y

sudo apt install openssh-server sshpass build-essential libssl-dev libffi-dev python3-dev \
bison flex git tcl-dev tcl tcl-tclreadline libreadline-dev autoconf libtool make automake \
texinfo pkg-config libusb-1.0-0 libusb-1.0-0-dev gcc-arm-none-eabi libnewlib-arm-none-eabi \
telnet python3 apt-utils libxslt-dev cmake curl python3-pip python3-venv -y

pip3 install gdown lxml simplejson

cp arch.tar.gz /home/sai vardhan/Desktop/fpga/arch.tar.gz

export INSTALL_DIR=/home/sai vardhan/Desktop/fpga/symbiflow
tar -C $INSTALL_DIR -xvf /home/sai vardhan/Desktop/fpga/arch.tar.gz
export PATH="$INSTALL_DIR/quicklogic-arch-defs/bin:$INSTALL_DIR/quicklogic-arch-defs/bin/python3:$PATH"
🧰 Setup QuickLogic FASM
bash
Copy
Edit
cd /home/sai vardhan/Desktop/fpga/pygmy-dev/tools/quicklogic-fasm
nvim requirements.txt
Replace contents of requirements.txt with:

bash
Copy
Edit
-e git+https://github.com/symbiflow/fasm.git#egg=fasm
-e git+https://github.com/antmicro/quicklogic-fasm-utils.git#egg=fasm-utils
bash
Copy
Edit
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
sudo python3 setup.py install
🔧 Build and Install QuickLogic Yosys Tools
bash
Copy
Edit
cd /home/sai vardhan/Desktop/fpga/pygmy-dev/tools/quicklogic-yosys
make config-gcc
make -j4 install PREFIX=$INSTALL_DIR
🔧 Install Symbiflow Plugins
bash
Copy
Edit
cd /home/sai vardhan/Desktop/fpga/pygmy-dev/tools/yosys-symbiflow-plugins
export PATH=$INSTALL_DIR/bin:$PATH
make -j4 install
🔧 Build Verilog-to-Routing Tool
bash
Copy
Edit
cd /home/sai vardhan/Desktop/fpga/pygmy-dev/tools/vtr-verilog-to-routing
make -j4
🔧 Update Bash Configuration
bash
Copy
Edit
nvim ~/.bashrc
Append these lines at the end of the file:

bash
Copy
Edit
export INSTALL_DIR=/home/sai vardhan/Desktop/fpga/symbiflow
export PATH="$INSTALL_DIR/quicklogic-arch-defs/bin:$INSTALL_DIR/quicklogic-arch-defs/bin/python3:$PATH"
export PATH=/home/sai vardhan/Desktop/fpga/symbiflow/bin:$PATH
bash
Copy
Edit
source ~/.bashrc
🧪 Test Installations
bash
Copy
Edit
vpr -h
yosys -h
qlfasm -h
ql_symbiflow -h
🧪 Compile Example Counter
bash
Copy
Edit
cd $INSTALL_DIR/quicklogic-arch-defs/tests/counter_16bit
ls
ql_symbiflow -compile -d ql-eos-s3 -P pd64 -v counter_16bit.v -t top -p chandalar.pcf -dump binary
pip3 install gdown lxml simplejson
ql_symbiflow -compile -d ql-eos-s3 -P pd64 -v counter_16bit.v -t top -p chandalar.pcf -dump binary
📁 Setup Example Projects
bash
Copy
Edit
cd /home/sai vardhan/Desktop/fpga
mkdir fpga-examples
cd fpga-examples
svn co https://github.com/gadepall/vaman/trunk/fpga/setup/codes/blink
cd blink
ls
🔨 Compile Example Project
bash
Copy
Edit
ql_symbiflow -compile -src /home/sai vardhan/Desktop/fpga/fpga-examples/blink \
-d ql-eos-s3 -P PU64 -v helloworldfpga.v -t helloworldfpga -p quickfeather.pcf -dump binary
Use nvim helloworldfpga.v to view/modify the Verilog code.

Use nvim quickfeather.pcf to configure pins.

Recompile the project after any modification.

📤 Upload Binary to Vaman Board
Make sure:

Vaman is in upload mode (green light ON)

Bin file is copied to /home/sai vardhan

bash
Copy
Edit
sudo python3 /home/sai vardhan/TinyFPGA-Programmer-Application/tinyfpga-programmer-gui.py \
--port /dev/ttyACM0 --appfpga /home/sai vardhan/helloworldfpga.bin --mode fpga

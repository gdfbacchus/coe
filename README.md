# Introducing Coengineer (beta)

Coengineer is a Delegated Proof of Stake blockchain loosely based on the Steem blockchain though there have been several changes and additions. Coengineer is a work in progress and there are likely to be some changes still before the full final version is released.



# No Support & No Warranty

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.

# Build Instructions

It is highly recommended to build Coengineer on Ubuntu 16.04. Coengineer requires a Boost version between 1.58 and 1.60 to build properly which is included in Ubuntu 16.04. Older versions of Ubuntu will require building a compatible version of Boost while newer versions of Ubuntu require rolling back to a previous Boost version. In the future a docker file will be included so that Coengineer can be built on any operating system but at present only manual build instructions for Ubuntu 16.04 are included. 

First install the dependencies:
  sudo apt-get install -y \
    autoconf \
    cmake3 \
    g++ \
    git \
    libssl-dev \
    libtool \
    make \
    pkg-config \
    doxygen \
    libncurses5-dev \
    libreadline-dev \
    libbz2-dev \
    python-dev \
    perl \
    python3 \
    python3-jinja2
    
Next we will need to install Boost packages:
  sudo apt-get install -y \
    libboost-chrono-dev \
    libboost-context-dev \
    libboost-coroutine-dev \
    libboost-date-time-dev \
    libboost-filesystem-dev \
    libboost-iostreams-dev \
    libboost-locale-dev \
    libboost-program-options-dev \
    libboost-serialization-dev \
    libboost-signals-dev \
    libboost-system-dev \
    libboost-test-dev \
    libboost-thread-dev
    
The following packages aren't required but are recommended:
  sudo apt-get install -y \
    doxygen \
    libncurses5-dev \
    libreadline-dev \
    perl
    
Now that we have installed the dependencies we can proceed to cloning from the repo and building the Coengineer software:

git clone https://github.com/gdfbacchus/coe

cd coe

git submodule update --init --recursive

mkdir build

cd build

cmake -DCMAKE_BUILD_TYPE=Release ..

make -j$(nproc) coengineerd

make -j$(nproc) cli_wallet

make install

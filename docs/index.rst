=======================
Schwabdev Documentation
=======================

.. image:: https://img.shields.io/discord/1076596998150561873?logo=discord
    :target: https://discord.gg/m7SSjr9rs9
    :alt: Discord Server

.. image:: https://img.shields.io/pypi/v/schwabdev
    :target: https://pypi.org/project/schwabdev/
    :alt: PyPI

.. image:: https://img.shields.io/pypi/dm/schwabdev
    :target: https://pypi.org/project/schwabdev/
    :alt: PyPI Downloads

.. image:: https://img.shields.io/badge/Donate-PayPal-green.svg
    :target: https://www.paypal.com/donate/?business=8VDFKHMBFSC2Q&no_recurring=0&currency_code=USD
    :alt: Donate

.. image:: https://img.shields.io/youtube/views/kHbom0KIJwc?style=flat&logo=youtube
    :target: https://youtube.com/playlist?list=PLs4JLWxBQIxpbvCj__DjAc0RRTlBz-TR8
    :alt: YouTube

.. image:: https://img.shields.io/github/license/tylerebowers/Schwab-API-Python
    :target: https://github.com/tylerebowers/Schwab-API-Python/blob/main/LICENSE.txt
    :alt: License

.. image:: https://img.shields.io/github/stars/tylerebowers/Schwab-API-Python?style=social
    :target: https://github.com/tylerebowers/Schwab-API-Python
    :alt: GitHub

Installation
------------

| :code:`pip install schwabdev`
| *You may need to use* :code:`pip3` *instead of* :code:`pip`

Quick setup
-----------

#. Setup your Schwab developer account `here <https://beta-developer.schwab.com/>`_.
    * Create a new Schwab individual developer app with callback url "https://127.0.0.1"
    * Add **both** API products to the app: "Accounts and Trading Production" and "Market Data Production".
    * Wait until the app status is "Ready for use", note that "Approved - Pending" will not work.
    * Enable TOS (Thinkorswim) for your Schwab account, it is needed for orders and other api calls.
#. Install packages
    * Install schwabdev :code:`pip install schwabdev`
    * *You may need to use :code:`pip3` instead of :code:`pip`*
#. Examples on how to use the client are in the :code:`examples/` folder (add your keys in the .env file)
    * The first time you run you will have to sign in to your Schwab account using the generated link in the terminal.
    * After signing in, agree to the terms, and select account(s). Then you will have to copy the link in the address bar and paste it into the terminal.
    * Questions? - join the `Discord group <https://discord.gg/m7SSjr9rs9>`_ or consult the :code:`/docs` folder.

.. code:: py

    import schwabdev #import the package

    client = schwabdev.Client('Your app key', 'Your app secret')  #create a client

    print(client.account_linked().json()) #make api calls


What can this program do?
-------------------------

* Authenticate and access the full api.
* Automatic token management and "access token" refreshes.
* Functions for all api functions (examples in :code:`examples/api_demo.py`)
* Stream real-time data with a customizable response handler (examples in :code:`examples/stream_demo.py`)
* Place orders and get order details (examples in :code:`examples/orders_demo.py`)
* Option for capture of callback urls when callback has a port (starts webserver on this port).
* Option for automatic starting/stopping of streamer when market opens/closes.
* Streaming stability with automatic restarts if the streamer crashes.

Notes
-----

| The schwabdev folder contains code for main operations:
* :code:`__init__.py` linker to client class.
* :code:`client.py` contains functions relating to api calls and requests.
* :code:`tokens.py` contains functions relating to token management.
* :code:`stream.py` contains functions for streaming data from websockets.

Youtube Tutorials
-----------------

#. `Authentication and Requests <https://www.youtube.com/watch?v=kHbom0KIJwc&ab_channel=TylerBowers>`_
#. `Streaming Real-time Data <https://www.youtube.com/watch?v=t7F2dUecgWc&list=PLs4JLWxBQIxpbvCj__DjAc0RRTlBz-TR8&index=2&ab_channel=TylerBowers>`_

*Github code has changed since these videos*

MIT Usage License
------------------

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
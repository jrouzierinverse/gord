# Configuration #

The configuration of GORD is contained in the `common.py` module.

  * Class: `Network`
    * `SERVICE_HOST`: (string) Host that the server is running on, e.g. the local hostname.
    * `SERVICE_PORT`: (int) Port to run on.
    * `AUTH_CLASS`: (string) Name of the authentication class from auth module to use.  Use AuthNone for a generic placeholder class which performs no authentication.
    * `USE_HTTPS`: (bool) Value instructing server to use https (True) or http (False).
    * `PEM_FILENAME`: (string) Value pointing to the PEM file for the https server, required only when `USE_HTTPS` is True, otherwise should be `None`.
  * Class: `AuthConfig`
    * `NO_AUTH_METHODS`: (list of strings) Method names that can be called without authentication.

# Installation and Use #

On the SCCM Data Provider Windows Server:

  1. Install ActivePython 2.4.
    * GORD may run on other versions of Python, but itâs only tested with ActivePython 2.4.
  1. Install [Tim Golden's WMI module](http://timgolden.me.uk/python/wmi/index.html).
  1. Choose an installation path (the default is `C:\GORD`).
    * If not using default installation path, edit `INSTALL_PATH` in `gord.py`.
  1. Configure settings in the `Network` and `AuthConfig` classes described above, if necessary.
  1. Open a command prompt (i.e. Start -> Run, type `cmd` and hit Enter).
  1. Run `install.bat`.
    * On success you will see, "Installing service GORD.  Service installed."
  1. Run `run.bat debug`.
    * On success you will see, "Debugging service GORD. The GORD service has started"
  1. Finally, to start the service, run `sc start gord`.
```python
# note that this notebook is not currently working correctly, there is a bug with the proxy config
```


```python
!pip install dash
!pip install dash==1.19.0
!pip install jupyter_dash
!pip install --upgrade plotly
```

    Requirement already satisfied: dash in ./opt/anaconda3/lib/python3.9/site-packages (1.19.0)
    Requirement already satisfied: dash-renderer==1.9.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (1.9.0)
    Requirement already satisfied: Flask>=1.0.4 in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (1.1.2)
    Requirement already satisfied: dash-core-components==1.15.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (1.15.0)
    Requirement already satisfied: plotly in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (5.15.0)
    Requirement already satisfied: flask-compress in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (1.13)
    Requirement already satisfied: future in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (0.18.2)
    Requirement already satisfied: dash-table==4.11.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (4.11.2)
    Requirement already satisfied: dash-html-components==1.1.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash) (1.1.2)
    Requirement already satisfied: Werkzeug>=0.15 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash) (2.0.3)
    Requirement already satisfied: Jinja2>=2.10.1 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash) (2.11.3)
    Requirement already satisfied: click>=5.1 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash) (8.0.4)
    Requirement already satisfied: itsdangerous>=0.24 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash) (2.0.1)
    Requirement already satisfied: brotli in ./opt/anaconda3/lib/python3.9/site-packages (from flask-compress->dash) (1.0.9)
    Requirement already satisfied: packaging in ./opt/anaconda3/lib/python3.9/site-packages (from plotly->dash) (21.3)
    Requirement already satisfied: tenacity>=6.2.0 in ./opt/anaconda3/lib/python3.9/site-packages (from plotly->dash) (8.0.1)
    Requirement already satisfied: MarkupSafe>=0.23 in ./opt/anaconda3/lib/python3.9/site-packages (from Jinja2>=2.10.1->Flask>=1.0.4->dash) (2.0.1)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in ./opt/anaconda3/lib/python3.9/site-packages (from packaging->plotly->dash) (3.0.9)
    Requirement already satisfied: dash==1.19.0 in ./opt/anaconda3/lib/python3.9/site-packages (1.19.0)
    Requirement already satisfied: dash-html-components==1.1.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (1.1.2)
    Requirement already satisfied: Flask>=1.0.4 in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (1.1.2)
    Requirement already satisfied: flask-compress in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (1.13)
    Requirement already satisfied: dash-renderer==1.9.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (1.9.0)
    Requirement already satisfied: dash-table==4.11.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (4.11.2)
    Requirement already satisfied: dash-core-components==1.15.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (1.15.0)
    Requirement already satisfied: plotly in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (5.15.0)
    Requirement already satisfied: future in ./opt/anaconda3/lib/python3.9/site-packages (from dash==1.19.0) (0.18.2)
    Requirement already satisfied: click>=5.1 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash==1.19.0) (8.0.4)
    Requirement already satisfied: itsdangerous>=0.24 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash==1.19.0) (2.0.1)
    Requirement already satisfied: Jinja2>=2.10.1 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash==1.19.0) (2.11.3)
    Requirement already satisfied: Werkzeug>=0.15 in ./opt/anaconda3/lib/python3.9/site-packages (from Flask>=1.0.4->dash==1.19.0) (2.0.3)
    Requirement already satisfied: brotli in ./opt/anaconda3/lib/python3.9/site-packages (from flask-compress->dash==1.19.0) (1.0.9)
    Requirement already satisfied: tenacity>=6.2.0 in ./opt/anaconda3/lib/python3.9/site-packages (from plotly->dash==1.19.0) (8.0.1)
    Requirement already satisfied: packaging in ./opt/anaconda3/lib/python3.9/site-packages (from plotly->dash==1.19.0) (21.3)
    Requirement already satisfied: MarkupSafe>=0.23 in ./opt/anaconda3/lib/python3.9/site-packages (from Jinja2>=2.10.1->Flask>=1.0.4->dash==1.19.0) (2.0.1)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in ./opt/anaconda3/lib/python3.9/site-packages (from packaging->plotly->dash==1.19.0) (3.0.9)
    Requirement already satisfied: jupyter_dash in ./opt/anaconda3/lib/python3.9/site-packages (0.4.2)
    Requirement already satisfied: ipykernel in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (6.15.2)
    Requirement already satisfied: nest-asyncio in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (1.5.5)
    Requirement already satisfied: ipython in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (7.31.1)
    Requirement already satisfied: ansi2html in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (1.8.0)
    Requirement already satisfied: retrying in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (1.3.4)
    Requirement already satisfied: dash in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (1.19.0)
    Requirement already satisfied: flask in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (1.1.2)
    Requirement already satisfied: requests in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter_dash) (2.28.1)
    Requirement already satisfied: dash-html-components==1.1.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (1.1.2)
    Requirement already satisfied: plotly in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (5.15.0)
    Requirement already satisfied: dash-table==4.11.2 in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (4.11.2)
    Requirement already satisfied: dash-core-components==1.15.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (1.15.0)
    Requirement already satisfied: future in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (0.18.2)
    Requirement already satisfied: flask-compress in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (1.13)
    Requirement already satisfied: dash-renderer==1.9.0 in ./opt/anaconda3/lib/python3.9/site-packages (from dash->jupyter_dash) (1.9.0)
    Requirement already satisfied: itsdangerous>=0.24 in ./opt/anaconda3/lib/python3.9/site-packages (from flask->jupyter_dash) (2.0.1)
    Requirement already satisfied: click>=5.1 in ./opt/anaconda3/lib/python3.9/site-packages (from flask->jupyter_dash) (8.0.4)
    Requirement already satisfied: Werkzeug>=0.15 in ./opt/anaconda3/lib/python3.9/site-packages (from flask->jupyter_dash) (2.0.3)
    Requirement already satisfied: Jinja2>=2.10.1 in ./opt/anaconda3/lib/python3.9/site-packages (from flask->jupyter_dash) (2.11.3)
    Requirement already satisfied: traitlets>=5.1.0 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (5.1.1)
    Requirement already satisfied: pyzmq>=17 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (23.2.0)
    Requirement already satisfied: debugpy>=1.0 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (1.5.1)
    Requirement already satisfied: jupyter-client>=6.1.12 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (7.3.4)
    Requirement already satisfied: tornado>=6.1 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (6.1)
    Requirement already satisfied: appnope in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (0.1.2)
    Requirement already satisfied: psutil in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (5.9.0)
    Requirement already satisfied: matplotlib-inline>=0.1 in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (0.1.6)
    Requirement already satisfied: packaging in ./opt/anaconda3/lib/python3.9/site-packages (from ipykernel->jupyter_dash) (21.3)
    Requirement already satisfied: pygments in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (2.11.2)
    Requirement already satisfied: pexpect>4.3 in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (4.8.0)
    Requirement already satisfied: pickleshare in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (0.7.5)
    Requirement already satisfied: prompt-toolkit!=3.0.0,!=3.0.1,<3.1.0,>=2.0.0 in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (3.0.20)
    Requirement already satisfied: backcall in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (0.2.0)
    Requirement already satisfied: decorator in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (5.1.1)
    Requirement already satisfied: jedi>=0.16 in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (0.18.1)
    Requirement already satisfied: setuptools>=18.5 in ./opt/anaconda3/lib/python3.9/site-packages (from ipython->jupyter_dash) (63.4.1)
    Requirement already satisfied: certifi>=2017.4.17 in ./opt/anaconda3/lib/python3.9/site-packages (from requests->jupyter_dash) (2022.9.24)
    Requirement already satisfied: charset-normalizer<3,>=2 in ./opt/anaconda3/lib/python3.9/site-packages (from requests->jupyter_dash) (2.0.4)
    Requirement already satisfied: urllib3<1.27,>=1.21.1 in ./opt/anaconda3/lib/python3.9/site-packages (from requests->jupyter_dash) (1.26.11)
    Requirement already satisfied: idna<4,>=2.5 in ./opt/anaconda3/lib/python3.9/site-packages (from requests->jupyter_dash) (3.3)
    Requirement already satisfied: six>=1.7.0 in ./opt/anaconda3/lib/python3.9/site-packages (from retrying->jupyter_dash) (1.16.0)
    Requirement already satisfied: parso<0.9.0,>=0.8.0 in ./opt/anaconda3/lib/python3.9/site-packages (from jedi>=0.16->ipython->jupyter_dash) (0.8.3)
    Requirement already satisfied: MarkupSafe>=0.23 in ./opt/anaconda3/lib/python3.9/site-packages (from Jinja2>=2.10.1->flask->jupyter_dash) (2.0.1)
    Requirement already satisfied: jupyter-core>=4.9.2 in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter-client>=6.1.12->ipykernel->jupyter_dash) (4.11.1)
    Requirement already satisfied: python-dateutil>=2.8.2 in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter-client>=6.1.12->ipykernel->jupyter_dash) (2.8.2)
    Requirement already satisfied: entrypoints in ./opt/anaconda3/lib/python3.9/site-packages (from jupyter-client>=6.1.12->ipykernel->jupyter_dash) (0.4)
    Requirement already satisfied: ptyprocess>=0.5 in ./opt/anaconda3/lib/python3.9/site-packages (from pexpect>4.3->ipython->jupyter_dash) (0.7.0)
    Requirement already satisfied: wcwidth in ./opt/anaconda3/lib/python3.9/site-packages (from prompt-toolkit!=3.0.0,!=3.0.1,<3.1.0,>=2.0.0->ipython->jupyter_dash) (0.2.5)
    Requirement already satisfied: brotli in ./opt/anaconda3/lib/python3.9/site-packages (from flask-compress->dash->jupyter_dash) (1.0.9)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in ./opt/anaconda3/lib/python3.9/site-packages (from packaging->ipykernel->jupyter_dash) (3.0.9)
    Requirement already satisfied: tenacity>=6.2.0 in ./opt/anaconda3/lib/python3.9/site-packages (from plotly->dash->jupyter_dash) (8.0.1)
    Requirement already satisfied: plotly in ./opt/anaconda3/lib/python3.9/site-packages (5.15.0)
    Requirement already satisfied: packaging in ./opt/anaconda3/lib/python3.9/site-packages (from plotly) (21.3)
    Requirement already satisfied: tenacity>=6.2.0 in ./opt/anaconda3/lib/python3.9/site-packages (from plotly) (8.0.1)
    Requirement already satisfied: pyparsing!=3.0.5,>=2.0.2 in ./opt/anaconda3/lib/python3.9/site-packages (from packaging->plotly) (3.0.9)



```python
from jupyter_dash.comms import _send_jupyter_config_comm_request
_send_jupyter_config_comm_request()
```


```python
import pandas as pd
import dash
import dash_html_components as html
import dash_core_components as dcc
from dash.dependencies import Input, Output
from jupyter_dash import JupyterDash
import plotly.graph_objects as go
```


```python
!pip list
```

    Package                       Version
    ----------------------------- --------------------
    alabaster                     0.7.12
    anaconda-client               1.11.0
    anaconda-navigator            2.4.0
    anaconda-project              0.11.1
    ansi2html                     1.8.0
    anyio                         3.5.0
    appdirs                       1.4.4
    applaunchservices             0.3.0
    appnope                       0.1.2
    appscript                     1.1.2
    argon2-cffi                   21.3.0
    argon2-cffi-bindings          21.2.0
    arrow                         1.2.2
    astroid                       2.11.7
    astropy                       5.1
    atomicwrites                  1.4.0
    attrs                         21.4.0
    Automat                       20.2.0
    autopep8                      1.6.0
    Babel                         2.9.1
    backcall                      0.2.0
    backports.functools-lru-cache 1.6.4
    backports.tempfile            1.0
    backports.weakref             1.0.post1
    bcrypt                        3.2.0
    beautifulsoup4                4.11.1
    binaryornot                   0.4.4
    bitarray                      2.5.1
    bkcharts                      0.2
    black                         22.6.0
    bleach                        4.1.0
    bokeh                         2.4.3
    boto3                         1.24.28
    botocore                      1.27.28
    Bottleneck                    1.3.5
    Brotli                        1.0.9
    brotlipy                      0.7.0
    certifi                       2022.9.24
    cffi                          1.15.1
    chardet                       4.0.0
    charset-normalizer            2.0.4
    click                         8.0.4
    cloudpickle                   2.0.0
    clyent                        1.2.2
    colorama                      0.4.5
    colorcet                      3.0.0
    conda                         23.1.0
    conda-build                   3.22.0
    conda-content-trust           0.1.3
    conda-pack                    0.6.0
    conda-package-handling        1.9.0
    conda-repo-cli                1.0.20
    conda-token                   0.4.0
    conda-verify                  3.4.2
    constantly                    15.1.0
    cookiecutter                  1.7.3
    cryptography                  37.0.1
    cssselect                     1.1.0
    cycler                        0.11.0
    Cython                        0.29.32
    cytoolz                       0.11.0
    daal4py                       2021.6.0
    dash                          1.19.0
    dash-core-components          1.15.0
    dash-html-components          1.1.2
    dash-renderer                 1.9.0
    dash-table                    4.11.2
    dask                          2022.7.0
    datashader                    0.14.1
    datashape                     0.5.4
    debugpy                       1.5.1
    decorator                     5.1.1
    defusedxml                    0.7.1
    diff-match-patch              20200713
    dill                          0.3.4
    distributed                   2022.7.0
    docutils                      0.18.1
    entrypoints                   0.4
    et-xmlfile                    1.1.0
    fastjsonschema                2.16.2
    filelock                      3.6.0
    flake8                        4.0.1
    Flask                         1.1.2
    Flask-Compress                1.13
    fonttools                     4.25.0
    fsspec                        2022.7.1
    future                        0.18.2
    gensim                        4.1.2
    glob2                         0.7
    gmpy2                         2.1.2
    greenlet                      1.1.1
    h5py                          3.7.0
    HeapDict                      1.0.1
    holoviews                     1.15.0
    hvplot                        0.8.0
    hyperlink                     21.0.0
    idna                          3.3
    imagecodecs                   2021.8.26
    imageio                       2.19.3
    imagesize                     1.4.1
    importlib-metadata            4.11.3
    incremental                   21.3.0
    inflection                    0.5.1
    iniconfig                     1.1.1
    intake                        0.6.5
    intervaltree                  3.1.0
    ipykernel                     6.15.2
    ipython                       7.31.1
    ipython-genutils              0.2.0
    ipywidgets                    7.6.5
    isort                         5.9.3
    itemadapter                   0.3.0
    itemloaders                   1.0.4
    itsdangerous                  2.0.1
    jdcal                         1.4.1
    jedi                          0.18.1
    jellyfish                     0.9.0
    Jinja2                        2.11.3
    jinja2-time                   0.2.0
    jmespath                      0.10.0
    joblib                        1.1.0
    json5                         0.9.6
    jsonschema                    4.16.0
    jupyter                       1.0.0
    jupyter_client                7.3.4
    jupyter-console               6.4.3
    jupyter_core                  4.11.1
    jupyter-dash                  0.4.2
    jupyter-server                1.18.1
    jupyterlab                    3.4.4
    jupyterlab-pygments           0.1.2
    jupyterlab-server             2.10.3
    jupyterlab-widgets            1.0.0
    keyring                       23.4.0
    kiwisolver                    1.4.2
    lazy-object-proxy             1.6.0
    libarchive-c                  2.9
    llvmlite                      0.38.0
    locket                        1.0.0
    lxml                          4.9.1
    lz4                           3.1.3
    Markdown                      3.3.4
    MarkupSafe                    2.0.1
    matplotlib                    3.5.2
    matplotlib-inline             0.1.6
    mccabe                        0.7.0
    mistune                       0.8.4
    mkl-fft                       1.3.1
    mkl-random                    1.2.2
    mkl-service                   2.4.0
    mock                          4.0.3
    mpmath                        1.2.1
    msgpack                       1.0.3
    multipledispatch              0.6.0
    munkres                       1.1.4
    mypy-extensions               0.4.3
    navigator-updater             0.3.0
    nbclassic                     0.3.5
    nbclient                      0.5.13
    nbconvert                     6.4.4
    nbformat                      5.5.0
    nest-asyncio                  1.5.5
    networkx                      2.8.4
    nltk                          3.7
    nose                          1.3.7
    notebook                      6.4.12
    numba                         0.55.1
    numexpr                       2.8.3
    numpy                         1.21.5
    numpydoc                      1.4.0
    olefile                       0.46
    openpyxl                      3.0.10
    packaging                     21.3
    pandas                        1.4.4
    pandocfilters                 1.5.0
    panel                         0.13.1
    param                         1.12.0
    parsel                        1.6.0
    parso                         0.8.3
    partd                         1.2.0
    pathlib                       1.0.1
    pathspec                      0.9.0
    patsy                         0.5.2
    pep8                          1.7.1
    pexpect                       4.8.0
    pickleshare                   0.7.5
    Pillow                        9.2.0
    pip                           22.2.2
    pkginfo                       1.8.2
    platformdirs                  2.5.2
    plotly                        5.15.0
    pluggy                        1.0.0
    ply                           3.11
    poyo                          0.5.0
    prometheus-client             0.14.1
    prompt-toolkit                3.0.20
    Protego                       0.1.16
    psutil                        5.9.0
    ptyprocess                    0.7.0
    py                            1.11.0
    pyasn1                        0.4.8
    pyasn1-modules                0.2.8
    pycodestyle                   2.8.0
    pycosat                       0.6.3
    pycparser                     2.21
    pyct                          0.4.8
    pycurl                        7.45.1
    PyDispatcher                  2.0.5
    pydocstyle                    6.1.1
    pyerfa                        2.0.0
    pyflakes                      2.4.0
    Pygments                      2.11.2
    PyHamcrest                    2.0.2
    PyJWT                         2.4.0
    pylint                        2.14.5
    pyls-spyder                   0.4.0
    pyobjc-core                   8.5
    pyobjc-framework-Cocoa        8.5
    pyobjc-framework-CoreServices 8.5
    pyobjc-framework-FSEvents     8.5
    pyodbc                        4.0.34
    pyOpenSSL                     22.0.0
    pyparsing                     3.0.9
    PyQt5-sip                     12.11.0
    pyrsistent                    0.18.0
    PySocks                       1.7.1
    pytest                        7.1.2
    python-dateutil               2.8.2
    python-lsp-black              1.2.1
    python-lsp-jsonrpc            1.0.0
    python-lsp-server             1.5.0
    python-slugify                5.0.2
    python-snappy                 0.6.0
    pytz                          2022.1
    pyviz-comms                   2.0.2
    PyWavelets                    1.3.0
    PyYAML                        6.0
    pyzmq                         23.2.0
    QDarkStyle                    3.0.2
    qstylizer                     0.1.10
    QtAwesome                     1.0.3
    qtconsole                     5.3.2
    QtPy                          2.2.0
    queuelib                      1.5.0
    regex                         2022.7.9
    requests                      2.28.1
    requests-file                 1.5.1
    retrying                      1.3.4
    rope                          0.22.0
    Rtree                         0.9.7
    ruamel.yaml                   0.17.21
    ruamel.yaml.clib              0.2.6
    ruamel-yaml-conda             0.15.100
    s3transfer                    0.6.0
    scikit-image                  0.19.2
    scikit-learn                  1.0.2
    scikit-learn-intelex          2021.20221004.121333
    scipy                         1.9.1
    Scrapy                        2.6.2
    seaborn                       0.11.2
    Send2Trash                    1.8.0
    service-identity              18.1.0
    setuptools                    63.4.1
    sip                           6.6.2
    six                           1.16.0
    smart-open                    5.2.1
    sniffio                       1.2.0
    snowballstemmer               2.2.0
    sortedcollections             2.1.0
    sortedcontainers              2.4.0
    soupsieve                     2.3.1
    Sphinx                        5.0.2
    sphinxcontrib-applehelp       1.0.2
    sphinxcontrib-devhelp         1.0.2
    sphinxcontrib-htmlhelp        2.0.0
    sphinxcontrib-jsmath          1.0.1
    sphinxcontrib-qthelp          1.0.3
    sphinxcontrib-serializinghtml 1.1.5
    spyder                        5.3.3
    spyder-kernels                2.3.3
    SQLAlchemy                    1.4.39
    statsmodels                   0.13.2
    sympy                         1.10.1
    tables                        3.6.1
    tabulate                      0.8.10
    TBB                           0.2
    tblib                         1.7.0
    tenacity                      8.0.1
    terminado                     0.13.1
    testpath                      0.6.0
    text-unidecode                1.3
    textdistance                  4.2.1
    threadpoolctl                 2.2.0
    three-merge                   0.1.1
    tifffile                      2021.7.2
    tinycss                       0.4
    tldextract                    3.2.0
    toml                          0.10.2
    tomli                         2.0.1
    tomlkit                       0.11.1
    toolz                         0.11.2
    tornado                       6.1
    tqdm                          4.64.1
    traitlets                     5.1.1
    Twisted                       22.2.0
    typing_extensions             4.3.0
    ujson                         5.4.0
    Unidecode                     1.2.0
    urllib3                       1.26.11
    w3lib                         1.21.0
    watchdog                      2.1.6
    wcwidth                       0.2.5
    webencodings                  0.5.1
    websocket-client              0.58.0
    Werkzeug                      2.0.3
    whatthepatch                  1.0.2
    wheel                         0.37.1
    widgetsnbextension            3.5.2
    wrapt                         1.14.1
    wurlitzer                     3.0.2
    xarray                        0.20.1
    xlrd                          2.0.1
    XlsxWriter                    3.0.3
    xlwings                       0.27.15
    yapf                          0.31.0
    zict                          2.1.0
    zipp                          3.8.0
    zope.interface                5.4.0



```python
# !jupyter labextension list
```


```python
spacex_df = pd.read_csv('https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/datasets/spacex_launch_dash.csv')
```


```python
# skeleton Dash app to be completed in this lab, downloaded from:
# https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DS0321EN-SkillsNetwork/labs/module_3/spacex_dash_app.py
# redundant lines commented out

# Import required libraries
# import pandas as pd
# import dash
# import dash_html_components as html
# import dash_core_components as dcc
# from dash.dependencies import Input, Output
import plotly.express as px

# Read the airline data into pandas dataframe
# spacex_df = pd.read_csv("spacex_launch_dash.csv")
max_payload = spacex_df['Payload Mass (kg)'].max()
min_payload = spacex_df['Payload Mass (kg)'].min()

# Create a dash application
# app = dash.Dash(__name__) # commented out as we are using JupyterDash instead of dash.Dash
app = JupyterDash(__name__)

# Create an app layout
app.layout = html.Div(children=[html.H1('SpaceX Launch Records Dashboard',
                                        style={'textAlign': 'center', 'color': '#503D36',
                                               'font-size': 40}),
                                # TASK 1: Add a dropdown list to enable Launch Site selection
                                # The default select value is for ALL sites
                                # dcc.Dropdown(id='site-dropdown',...)
                                dcc.Dropdown(id='site-dropdown',
                                             options=[
                                                     {'label': 'All Sites', 'value': 'ALL'},
                                                     {'label': 'CCAFS LC-40', 'value': 'CCAFS LC-40'},
                                                     {'label': 'VAFB SLC-4E', 'value': 'VAFB SLC-4E'},
                                                     {'label': 'KSC LC-39A', 'value': 'KSC LC-39A'},
                                                     {'label': 'CCAFS SLC-40', 'value': 'CCAFS SLC-40'}
                                                     ],
                                             value='ALL',
                                             placeholder='Select a Launch Site here',
                                             searchable=True
                                             # style={'width':'80%','padding':'3px','font-size':'20px','text-align-last':'center'}
                                             ),
                                html.Br(),

                                # TASK 2: Add a pie chart to show the total successful launches count for all sites
                                # If a specific launch site was selected, show the Success vs. Failed counts for the site
                                html.Div(dcc.Graph(id='success-pie-chart')),
                                html.Br(),

                                html.P("Payload range (Kg):"),
                                # TASK 3: Add a slider to select payload range
                                #dcc.RangeSlider(id='payload-slider',...)
                                dcc.RangeSlider(id='payload-slider',
                                                min=0,
                                                max=10000,
                                                step=1000,
                                                value=[min_payload, max_payload]
                                                ),

                                # TASK 4: Add a scatter chart to show the correlation between payload and launch success
                                html.Div(dcc.Graph(id='success-payload-scatter-chart')),
                                ])

# TASK 2:
# Add a callback function for `site-dropdown` as input, `success-pie-chart` as output
@app.callback(Output(component_id='success-pie-chart', component_property='figure'),
              Input(component_id='site-dropdown', component_property='value'))
def get_pie_chart(entered_site):
    filtered_df = spacex_df
    if entered_site == 'ALL':
        fig = px.pie(filtered_df, values='class', 
        names='Launch Site', 
        title='Success Count for all launch sites')
        return fig
    else:
        # return the outcomes piechart for a selected site
        filtered_df=spacex_df[spacex_df['Launch Site']== entered_site]
        filtered_df=filtered_df.groupby(['Launch Site','class']).size().reset_index(name='class count')
        fig=px.pie(filtered_df,values='class count',names='class',title=f"Total Success Launches for site {entered_site}")
        return fig

# TASK 4:
# Add a callback function for `site-dropdown` and `payload-slider` as inputs, `success-payload-scatter-chart` as output
@app.callback(Output(component_id='success-payload-scatter-chart',component_property='figure'),
                [Input(component_id='site-dropdown',component_property='value'),
                Input(component_id='payload-slider',component_property='value')])
def scatter(entered_site,payload):
    filtered_df = spacex_df[spacex_df['Payload Mass (kg)'].between(payload[0],payload[1])]
    # thought reusing filtered_df may cause issues, but tried it out of curiosity and it seems to be working fine
    
    if entered_site=='ALL':
        fig=px.scatter(filtered_df,x='Payload Mass (kg)',y='class',color='Booster Version Category',title='Success count on Payload mass for all sites')
        return fig
    else:
        fig=px.scatter(filtered_df[filtered_df['Launch Site']==entered_site],x='Payload Mass (kg)',y='class',color='Booster Version Category',title=f"Success count on Payload mass for site {entered_site}")
        return fig

# Run the app
if __name__ == '__main__':
    app.run_server(mode='inline', host='localhost')
 
```



<iframe
    width="100%"
    height="650"
    src="http://localhost:8050/"
    frameborder="0"
    allowfullscreen

></iframe>




```python

```

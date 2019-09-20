### venv
---
https://github.com/python/cpython/tree/3.7/Lib/venv/

https://docs.python.org/3/library/venv.html

```py
// cpython/Lib/venv/__init.py

logger = logging.getLogger(__name__)

class EnvBuilder:
  def __init__(self, system_site_packages=False, clear=False,
      symlinks=False, upgrade=False, with_pip=False, prompt=None):
    self.system_site_packages = system_site_packages
    self.clear = clear
    self.symlinks = symlinks
    self.upgrade = upgrade
    self.with_pip = with_pip
    self.prompt = prompt
    
  def create(self, env_dir):
    env_dir = os.path.abspath(env_dir)
    context = self.ensure_directories(env_dir)
    true_systems_site_packages = self.system_site_packages
    self.system_site_packages = False
    self.create_configuration(context)
    if self.with_pip:
      self._setup_pip(context)
    if not self.upgrade:
      self.setup_scripts(context)
      self.post_setup(context)
    if true_system_site_packages:
      self.system_site_packages = True
      self.create_configuration(context)
      
  def clear_directory(self, path):
  
  def ensure_directories(self, env_dir):
  
  
  
```

```
```

```
```

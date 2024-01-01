# ansible_role_ensure_helm_state

Basic installation or removal of helm package manager, currently just debian is supported.  

## Requirements

Debian 11, 12

## Role Variables

```yaml
helm_state
helm_apt_key
helm_apt_repository_string
```

**helm_state:** State of the helm installatin can be either present or absent
**helm_apt_key**: URL to signing apt key of the helm deb package
**helm_apt_repository_string:** Apt repository string for the helm deb package

## Development

### Testing

* Create venv: `python3 -m venv ./venv`
* Install pip requirements: `venv/bin/pip install -r pip_requirements.txt`
* Execute tests `venv/bin/molecule test`

### Linting & static security analyser

Both the linter and the static security analyser are running on each push on the github actions pipeline.  

* As linter [ansible-lint](https://ansible.readthedocs.io/projects/lint/) is used. For installation documentation see [ansible lint installing](https://ansible.readthedocs.io/projects/lint/)
  * Just run `ansible-lint`

* To check if there are any passwords, tokens... hardcoded, [kics](https://kics.io/index.html) is used to ensure a secure IaC repository.  
  * Run it locally `docker run -t -v $PWD:/path checkmarx/kics:latest scan -p /path -o "/path/"`

## Dependencies

None.

## License

GNU General Public License version 3

# custom-pattern-secrets

Custom Secret Scanning Patterns repository.

## Patterns

{% for path, config in configs.items() %}
{%- if config.display  %}

### [{{ config.name }}]({{ config.path.replace("/patterns.yml", "") }})

{% for pattern in config.patterns %}
{%- if pattern.experimental == False %}

- {{ pattern.name }}
  {%- endif %}
  {%- endfor %}
  {% endif %}
  {%- endfor %}

## Usage Documentation

### Basic Usage

To use the Secret Scanning Tools, follow these steps:

1. Install the required dependencies using `pipenv install`.
2. Run the desired command using `pipenv run <command>`.

### Advanced Configuration

You can configure the Secret Scanning Tools with additional options:

```yaml
- name: Secret Scanning Test Suite
  uses: advanced-security/secret-scanning-tools@v1
  with:
    # Modes to run
    # > 'validate' (default), 'all', 'snapshot', 'markdown'
    mode: 'validate'
```

### Local Testing

To test the Secret Scanning Tools locally, follow these steps:

1. Change directory to `secretscanning`.
2. Run `make requirements` to install the required dependencies.
3. Run the test script using `./test.py`.

For full usage instructions, use `./test.py --help`.

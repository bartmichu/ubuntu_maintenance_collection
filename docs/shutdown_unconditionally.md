# shutdown_unconditionally playbook

This playbook performs an unconditional system shutdown on Ubuntu systems. It's a straightforward way to shut down target machines.

Use it with caution, as it will shut down the target systems regardless of their current state. Make sure you understand the implications before running it.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `system_shutdown`

## Variables

This playbook does not use any input variables.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).

## Author

Michał Bartkowiak

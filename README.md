# pythoninthegrass' opinionated vib image

## Use my custom image

### But why tho?

Some quality of life packages are pre-installed:

* `ptyxis`: container-aware terminal
  * Nicer alternative to Blackbox IMHO
* `docker`: OG container runtime
  * For those who need/want to use Docker over Podman
  * Podman is still available and the `vso shell` container image is Podman-based
* `ansible`: configuration management
* `bat`: cat clone with wings
* `build-essential`: build tools
* A number of [other packages](recipe.yml#L40-L74) primarily for development

The ethos of immmutable OSes like Vanilla OS is to run everything in containers or Flatpaks, this is a happy medium that enables an easier transition for those who are used to running things on the host.

It also speeds up the initial onboarding since less packages need to be layered via `abroot` post-install.

### Quickstart

Point ABRoot to pythoninthegrass' custom image to use it.

* Open a terminal and run `vso shell`
  * Default with `Blackbox`, only necessary over SSH or another terminal
* Edit the configuration file with the command: `abroot config-editor`
* Change the "name" entry from something like `vanilla-os/desktop` to `pythoninthegrass/vanillaos`
* Now, run `abroot upgrade` to switch to the custom image

**Exhibit A**:

```json
{
  "registry": "ghcr.io",
  "registryService": "registry.ghcr.io",
  "registryAPIVersion": "v2",
  "name": "pythoninthegrass/vanillaos",
  "tag": "main",
}
```

## Further Reading

> [!TIP]
> It is suggested to check the [Vib documentation](https://docs.vanillaos.org/collections/vib) to know more about the recipe format, structure of modules and the supported fields.

* [Vib images](https://github.com/Vanilla-OS/Vib)
* [Official Vanilla OS images](https://images.vanillaos.org)

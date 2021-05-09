# pi-0-w-builder
a template for embedded pi zero w projects

## This template is meant for embedded raspberry pi projects.
- the goal is, to package your project into a ready to use pi os image
- we build the image by using chroot & qemu
- image gets pushed into a Release
- workflow is executed by GitHub actions
- can be easily modified to your needs

### quickstart:
1. copy setup into the root of your project
2. copy build-pi-0-w.yaml into your workflows folder
3. edit both files to your needs

### what to edit in the workflow file:
- line 29: base image to use (default: raspios_lite:2021-03-04)
- line 30: target path repo (default: /home/pi/pi-0-w)
- line 41, 43, 45, 63: the images filename (default: pi-0-w)
- line 9, 19-21, 46: branch to build for latest release (default: main)

### what to edit in the setup file:
- line 42 & 43: set the hostname (default: pi-zero-w)
- line 46 & 47: set timezoen (default: Europe/Berlin)
- line 49 & following: insert your script

### defaults:
- every push into the main branch builds a new release called development image with the tag :latest
- every version tag builds a fitting release called by the version number

### how to tag in git:
```bash
# to tag your head:
git tag v0.0.1

# to push the tag:
git push origin v0.0.1

```

### Advice:
Of course it's also possible, to execute a ansible playbook you've put into your repository.
This way, you make sure, that people are using the same setup of your application, no matter how they've installed it.
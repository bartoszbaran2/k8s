# Helm -> helm.sh

Package manager for k8s

Like:
- pip (python)
- npm (js)
- java (maven/gradle)
- apt (ubuntu)
- homebrew (macos)
- chocolatey (windows)

---

- tool for managing Kubernetes packages called charts
- helm client - cli user
- helm library - logic for executing operations

## Chart
- bundle of information used to create an instance of k8s application

## Config 
- configuration information that can be merged into a packaged chart to create releasable object.

## Release
- running instance of a chart (combined with specific configuration) in k8s
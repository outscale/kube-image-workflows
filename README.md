## **Kubernetes Image Building Workflows**

[![Project Stage](https://docs.outscale.com/fr/userguide/_images/Project-Sandbox-yellow.svg)](https://docs.outscale.com/en/userguide/Open-Source-Projects.html) [![](https://dcbadge.limes.pink/api/server/HUVtY5gT6s?style=flat&theme=default-inverted)](https://discord.gg/HUVtY5gT6s)

<p align="center">
  <img alt="Kubernetes Logo" src="https://upload.wikimedia.org/wikipedia/commons/3/39/Kubernetes_logo_without_workmark.svg" width="120px">
</p>

---

## 🌐 Links

- Join our community on [Discord](https://discord.gg/HUVtY5gT6s)

---

## 📄 Table of Contents

- [Overview](#-overview)
- [List of images](#-list-of-images)
- [Releasing new images](#-releasing-new-images)
- [License](#-license)
- [Contributing](#-contributing)

---

## 🧭 Overview

**Kubernetes Image Building Workflows** is a repository containing the workflows used to build the Kubernetes OMIs published under the "Outscale Open-Source" account.

These OMIs are intended for use in creating Kubernetes clusters with [CAPOSC](https://github.com/outscale/cluster-api-provider-outscale).

The images are built using the [Kubernetes Image Builder](https://github.com/kubernetes-sigs/image-builder) and are deployed on 3 regions: eu-west-2, us-east-2 and cloudgouv-eu-west-1 using the same name.

The images are produced by an open-source builder. There is no guarantee that clusters created with these images will be fully functional, and no official support is provided by Outscale.

---

## 📋 List of images

See releases.

For each version of Kubernetes, 2 images are built: one based on Ubuntu 22.04, one based on Ubuntu 24.04.

---

## 🚀 Releasing new images

The runc version is defined by the RUNC_VERSION variable.
The containerd version is defined by the CONTAINERD_VERSION variable.

New images are built when a new tag is pushed. The tag name defines the Kubernetes version to use.

```shell
export RELEASE_TAG=v1.33.6
git tag -s ${RELEASE_TAG} -m "🔖 Kubernetes ${RELEASE_TAG}"
git push origin ${RELEASE_TAG}
```

When re-releasing a previously released Kubernetes version, a `/[some additional comment]` suffix can be added to the tag, it will be ignored.

```shell
export RELEASE_TAG=v1.33.6/runc-1.2.6
git tag -s ${RELEASE_TAG} -m "🔖 Kubernetes ${RELEASE_TAG}"
git push origin ${RELEASE_TAG}
```

---

## 📜 License

**Kubernetes Image Building Workflows** is released under the BSD 3-Clause license.

© 2025 Outscale SAS

See [LICENSE](./LICENSE) for full details.

---

## 🤝 Contributing

We welcome contributions!

Please read our [Contributing Guidelines](CONTRIBUTING.md) and [Code of Conduct](CODE_OF_CONDUCT.md) before submitting a pull request.

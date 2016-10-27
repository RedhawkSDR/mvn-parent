# Eclipse Neon Subset

## Description

The REDHAWK Explorer / IDE 2.0 series is based on Eclipse Mars which contains several graphics-related bugs that manifest with in CentOS 7 (due to GTK3). This project produces a patch repo that allows some newer bundles from Eclipse Neon to be installed in our products.

The project executes as follows:
1. `neon-subset` mirrors several bundles, their source, and their fragments from Eclipse Neon:
  * `org.eclipse.swt`
  * `org.eclipse.jface.text`
  * `org.eclipse.equinox.common`
2. Several Eclipse features are built. Their versions are bumped at the service level (e.g 1.0.0 to 1.0.1), and their required versions of the bundles we mirrored in the previous step are replaced:
  * `org.eclipse.e4.rcp`
  * `org.eclipse.rcp`
  * `org.eclipse.platform`
  * `org.eclipse.sdk`
3. `patch-repo` assembles the mirrored bundles from step 1 along with our replacement features from step 2 into a p2 repository.

## Building

Ensure you have a JDK and Maven installed and on your path. Execute:

```bash
mvn install
```

The mirrored repository will be located under `patch-repo/target/repository`.


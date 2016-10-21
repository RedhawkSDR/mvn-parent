# Eclipse Neon Subset

## Description

The REDHAWK Explorer / IDE 2.0 series is based on Eclipse Mars which contains several graphics-related bugs that manifest with in CentOS 7 (due to GTK3). This project produces a patch repo that allows some newer bundles from Eclipse Neon to be installed in our products.

The project executes as follows:
1. `neon-subset` mirrors `org.eclipse.swt` (and fragments) and `org.eclipse.jface.text` from Eclipse Neon
2. `org.eclipse.e4.rcp` produces a modified version of that feature which includes `org.eclipse.swt` from Eclipse Neon
3. `org.eclipse.rcp` produces a modified version of that feature which includes our new `org.eclipse.e4.rcp` feature
3. `patch-repo` assembles the our two replacement features and our plugins from Neon into a p2 repository

## Building

Ensure you have a JDK and Maven installed and on your path. Execute:

```bash
mvn install
```

The mirrored repository will be located under `patch-repo/target/repository`.


+++
date = "2017-08-17T13:47:08+02:00"
tags = []
title = "Copy directories and files to and from Kubernetes Container [POD]"
+++

As we all know about SCP Linux command to Copy the files and directories from a remote host to the local host and vice versa over **SSH**.
Similar to that we have ‘**KUBECTL CP**’ to Copy the files and directories from a Kubernetes Container [POD] to the local host and vice versa.


## Syntax:

    kubectl cp <file-spec-src> <file-spec-dest>

POD in a specific container

    kubectl cp <file-spec-src> <file-spec-dest> -c <specific-container>

**Copy /tmp/foo local file to /tmp/bar in a remote pod in namespace**

    kubectl cp /tmp/foo <some-namespace>/<some-pod>:/tmp/bar

**Copy /tmp/foo from a remote pod to /tmp/bar locally**

    kubectl cp <some-namespace>/<some-pod>:/tmp/foo /tmp/bar

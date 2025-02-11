# local-ai-container

## Build

To build the container, run:

```sh
singularity build --nv --fakeroot --sandbox --tmpdir=/mnt/data/tmp deepseek-v1.0.0-sandbox deepseek-v1.0.0.def
```

> **Note:** Ensure that the temporary path specified in `--tmpdir` is a directory with `777` permissions. This is necessary for the build process to complete successfully.

## Start Instance

To start a instance of the container, run:

```sh
singularity instance start --nv --writable deepseek-v1.0.0-sandbox deepseek-v1.0.0-instance
```

## Log into Instance

To log in a running instace and have access to Ollama, Open WebUI and other packages, run:

```sh
singularity shell instance://deepseek-v1.0.0-instance
```

### List Available Models in Ollama

To list the available local models, run:

```sh
ollama list
```

### List Running Models in Ollama

To list the available local models, run:

```sh
ollama ps
```

### Pull a Model

To pull a new model from the repository, run:

```sh
ollama pull deepseek-r1:7b
```

## Accessing Open WebUI in the Browser

To access Open WebUI in your browser, follow these steps:

1. Ensure the container instance is running.
2. Open your web browser.
3. Navigate to the following URL.

### Running in Local Machine

Just navigate to the following URL:

```sh
https://localhost:8080
```

### Running in Remote Server

To access Open WebUI running on a remote server, you need to create an SSH tunnel. This will forward the remote server's port to your local machine, allowing you to access the web interface in your local browser.

```sh
ssh -L 8081:localhost:8080 user@server
```

Then, in your local machine, navigate to the following URL:

```sh
https://localhost:8081
```


<!-- ```sh
```

```sh
```

```sh
``` -->
# TYPO3-build 👷

## How to build a Docker container

1. Go to the target directory e.g `cd php73`
2. Build and deploy Docker container. Ensure you have the required rights to push into the HDNET organization.
 
    ```bash
    docker login 
    docker build -f ./Dockerfile -t hdnet/typo3-build:<TAG> . 
    docker push hdnet/typo3-build:<TAG>    
    ```
 Use docker buildx to build and push multi-arch images.
 
    ```bash
	docker buildx build \
	 --push \
	 --platform linux/amd64,linux/arm64 \
	 -f ./Dockerfile \
	 -t hdnet/typo3-build:<TAG> .
    ```
 
 
## Images

Directory | Image
----------- | ------------
`/php70` | hdnet/typo3-build:php7.0
`/php71` | hdnet/typo3-build:php7.1
`/php73` | hdnet/typo3-build:php7.3
`/php74` | hdnet/typo3-build:php7.4
`/php74-node-lts` | hdnet/typo3-build:php7.4-node-lts
`/php80-node-lts` | hdnet/typo3-build:php8.0-node-lts
`/php80-node-16` | hdnet/typo3-build:php8.0-node-16
`/php81-node-lts` | hdnet/typo3-build:php8.1-node-lts


# pixelmon
Repository for a Docker image of the Pixelmon Minecraft mod

# Usage
Use ./run.sh to run or use below setup for docker-compose

```
services:
  pixelmon:
    container_name: pixelmon
    image: walthowd/pixelmon
    ports:
      - 25565:25565
    volumes:
      - /opt/pixelmon/ops/ops.json:/opt/minecraft/ops.json
      - /opt/pixelmon/server.properties:/opt/minecraft/server.properties
      - /opt/pixelmon/config:/opt/minecraft/config
      - /opt/pixelmon/world:/opt/minecraft/world
    restart: on-failure
    environment:
      MINECRAFT_DIR: /opt/minecraft
 ```

You can disable the extra mods (ExtraUtils, Refined Storage, Pixel Extras, Just Enough Items) by setting the EXTRA_UTILS, REFINED_STORAGE, PIXEL_EXTRAS or JEI to false. 

You can also set JAVA_EXTRA_PARAM to any additional flags you want to pass to increase RAM, etc.

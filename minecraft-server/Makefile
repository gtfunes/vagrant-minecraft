.PHONY: all clean

all:
	docker run \
		--restart always \
		--detach \
		--name minecraft \
		--publish 25565:25565 \
		--env EULA=true \
		--env SERVER_NAME=MCServer \
		--env DIFFICULTY=normal \
		--env ALLOW_NETHER=true \
		--env ALLOW_END=true \
		--env PVP=true \
		--env ANNOUNCE_PLAYER_ACHIEVEMENTS=true \
		--env GENERATE_STRUCTURES=true \
		--env MEMORY=2G \
		--volume $(MC_HOME)/minecraft:/data \
		itzg/minecraft-server

clean:
	docker ps -a | grep minecraft && docker rm -f -v minecraft || true

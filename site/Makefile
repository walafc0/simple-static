# You should only modify theses three lines
REMOTE=user@server.com:/path/to/web/server/
SS=/usr/local/bin/ss
SITE=./src

BIN=$(SITE).static
RM=rm -rf

.PHONY: all clean local install deploy

all: local

local:
	$(SS) $(SITE)

install:
	rsync -avz $(SITE).static/ $(REMOTE)

clean:
	$(RM) $(BIN)

deploy: clean local install

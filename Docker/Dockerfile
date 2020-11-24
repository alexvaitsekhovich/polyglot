FROM ubuntu:18.04
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
	apt-get -y upgrade && \
	apt-get install -y curl && \
    apt-get install -y nano

# C
RUN apt install -y build-essential

# Ada
RUN apt-get install -y gnat

# Elixir
RUN apt-get install -y elixir && \
		apt-get install -y --no-install-recommends locales && \ 
		locale-gen de_DE.UTF-8 &&\
		export LANG=en_US.UTF-8 && \
		echo $LANG UTF-8 > /etc/locale.gen && \
		locale-gen && \
		update-locale LANG=$LANG

ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8 

# Go
RUN apt-get install -y golang-go

# Haskell
RUN apt-get install -y haskell-platform

# Java
RUN apt-get install -y default-jdk

# Clojure
RUN apt-get install -y bash curl rlwrap && \
	curl -O https://download.clojure.org/install/linux-install-1.10.1.469.sh && \
	chmod +x linux-install-1.10.1.469.sh && \
	./linux-install-1.10.1.469.sh && clj

# Julia
RUN apt install wget && \
	wget https://julialang-s3.julialang.org/bin/linux/x64/1.0/julia-1.0.0-linux-x86_64.tar.gz && \
	tar xvfa julia-1.0.0-linux-x86_64.tar.gz -C /lib/ && \
	rm julia-1.0.0-linux-x86_64.tar.gz

ENV PATH "$PATH:/lib/julia-1.0.0/bin/"

# Lua    
RUN apt-get install lua5.3 -y && \
	# echo "alias lua=lua5.3" >> ~/.bashrc
	ln -s /usr/bin/lua5.3 /usr/bin/lua

# Nim
RUN apt-get install -y nim

# Node.js
RUN apt-get install -y nodejs

# OCaml
RUN apt install -y ocaml

# Pascal 
RUN apt-get install -y fp-compiler 

# Perl is there

# PHP
RUN apt-get install -y php

# Python
RUN apt-get install -y python

# R
RUN apt-get install -y r-base

# Ruby
RUN apt install -y ruby-full

# Rust
RUN curl https://sh.rustup.rs -sSf | bash -s -- -y
ENV PATH "$PATH:/root/.cargo/bin"

# Scala
RUN wget www.scala-lang.org/files/archive/scala-2.12.6.deb && \ 
	dpkg -i scala-2.12.6.deb


# Kotlin & Groovy
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
RUN apt-get install -y unzip
RUN apt-get install -y zip
RUN curl -s https://get.sdkman.io | bash
RUN chmod a+x "$HOME/.sdkman/bin/sdkman-init.sh"
RUN source "$HOME/.sdkman/bin/sdkman-init.sh" && \
	sdk install kotlin && \
	sdk install groovy && \
	ln -s /root/.sdkman/candidates/kotlin/current/bin/kotlin /usr/bin/kotlin && \
	ln -s /root/.sdkman/candidates/kotlin/current/bin/kotlinc /usr/bin/kotlinc && \
	ln -s /root/.sdkman/candidates/groovy/current/bin/groovy /usr/bin/groovy
# C#
RUN apt-get install -y mono-complete

# F#
RUN apt install mono-complete fsharp

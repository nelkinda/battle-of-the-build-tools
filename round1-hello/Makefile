TOOLS:=ant gradle maven sbt make
LOOPS:=10

SHELL:=/bin/bash
.ONESHELL:

.PHONY: all
all: $(addsuffix -all,$(TOOLS))
%-all:
	$(MAKE) -C hello-$* all

.PHONY: clean
clean: $(addsuffix -clean,$(TOOLS))
%-clean:
	$(MAKE) -C hello-$* clean

.PHONY: all-performance clean-performance
all-performance: $(addsuffix -all-performance,$(TOOLS))
clean-performance: $(addsuffix -clean-performance,$(TOOLS))
%-performance:
	start=$$(date +%s.%N)
	for ((i = 0; i < $(LOOPS); i++)) ; do $(MAKE) $* >/dev/null 2>/dev/null ; done
	end=$$(date +%s.%N)
	duration=$$(echo -e "scale=10\\n($$end - $$start) / $(LOOPS)" | bc)
	echo $*: $$duration

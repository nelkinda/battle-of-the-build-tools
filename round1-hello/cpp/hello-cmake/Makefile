.PHONY: all
all: build/
	make -C $^

build/:
	mkdir -p $@
	cd $@ && cmake ../

.PHONY: clean
clean::
	$(RM) -r build/

SBT:=./sbt
SBTFLAGS:=
BUILD:=$(SBT)
BUILDFLAGS:=
GOAL_DEFAULT:=package
OUTPUT_DIR:=target/classes/

.PHONY: all
## Builds and verifies the project.
all: $(GOAL_DEFAULT)

.PHONY: $(GOAL_DEFAULT)
## Builds and verifies the project.
$(GOAL_DEFAULT): $(BUILD)
	$(BUILD) $(BUILDFLAGS) $@

.PHONY: clean
clean:: $(BUILD)
	$(BUILD) $(BUILDFLAGS) $@

.PHONY: run
run:
	java -cp $(OUTPUT_DIR) com.nelkinda.blog.botbt.hello.Hello

.PHONY: wrapper
## Generates the wrapper.
wrapper: $(BUILD)
$(BUILD):
	curl -Ls https://git.io/sbt >$@ && chmod +x $@

-include ~/.User.mk
-include ../.User.mk
-include .User.mk

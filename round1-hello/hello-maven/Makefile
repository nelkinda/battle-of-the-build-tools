MVN:=./mvnw
MVNFLAGS:=
BUILD:=$(MVN)
BUILDFLAGS:=$(MVNFLAGS)
MVN_BOOTSTRAP:=$(firstword $(wildcard $(MAVNE) $(shell which mvn)))
GOAL_DEFAULT:=package
OUTPUT_DIR:=target/classes/
MVN_WRAPPER:=io.takari:maven:0.7.7

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
	$(MVN_BOOTSTRAP) -N $(MVN_WRAPPER):wrapper

-include ~/.User.mk
-include ../.User.mk
-include .User.mk

GRADLE:=./gradlew
GRADLEFLAGS:=--warning-mode all
BUILD:=$(GRADLE)
BUILDFLAGS:=$(GRADLEFLAGS)
GRADLE_BOOTSTRAP:=$(firstword $(wildcard $(MAVNE) $(shell which gradle)))
GOAL_DEFAULT:=build
OUTPUT_DIR:=build/classes/java/main/

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
	$(GRADLE_BOOTSTRAP) wrapper

-include ~/.User.mk
-include ../.User.mk
-include .User.mk

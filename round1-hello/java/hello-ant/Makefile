ANT:=./.ant/apache-ant-1.10.7/bin/ant
ANTFLAGS:=
BUILD:=$(ANT)
BUILDFLAGS:=$(ANTFLAGS)
GOAL_DEFAULT:=dist
OUTPUT_DIR:=classes/

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

$(BUILD): .ant/apache-ant-1.10.7-bin.tar.gz
	tar xzf $^ -C .ant/
	touch $@

.ant/apache-ant-1.10.7-bin.tar.gz: | .ant/
	wget http://mirrors.estointernet.in/apache//ant/binaries/apache-ant-1.10.7-bin.tar.gz -O .ant/apache-ant-1.10.7-bin.tar.gz

.ant/:
	mkdir -p $@

-include ~/.User.mk
-include ../.User.mk
-include .User.mk

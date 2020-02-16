OUTPUT_DIR:=classes/main/java/
SOURCE_FILES:=$(shell find src/main/java/ -name "*.java")

.PHONY: all
## Builds and verifies the project.
all: package

.PHONY: package
## Builds and verifies the project.
package: hello.jar

hello.jar: $(OUTPUT_DIR)
	jar cf $@ -C $(OUTPUT_DIR) ./

$(OUTPUT_DIR): $(SOURCE_FILES)
	mkdir -p $@
	javac -sourcepath src/main/java/ -d $(OUTPUT_DIR) $(SOURCE_FILES)
	touch $@

.PHONY: clean
clean::
	$(RM) -r classes/ hello.jar

.PHONY: run
run:
	java -cp $(OUTPUT_DIR) com.nelkinda.blog.botbt.hello.Hello

.PHONY: watch
watch:
	while true ; do $(MAKE) -s ; echo -n "." ; inotifywait -qqre close_write src/ ; done

-include ~/.User.mk
-include ../.User.mk
-include .User.mk

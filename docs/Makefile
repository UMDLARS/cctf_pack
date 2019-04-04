source = instructions.md
output = www/instructions.html

.PHONY: all

all: clean $(output)

clean:
	rm -f $(output)

$(output):
	pandoc --css pandoc.css --from markdown_github -s -o $(output) $(source)

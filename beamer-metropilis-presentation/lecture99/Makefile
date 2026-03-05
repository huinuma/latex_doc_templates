LATEXMK := latexmk
MAIN := slides.tex
NOTE_MAIN := slides_note.tex
BUILD_DIR := build

.PHONY: all slide note clean distclean

all: slide

$(BUILD_DIR):
	mkdir -p $(BUILD_DIR)

slide: $(BUILD_DIR)
	$(LATEXMK) -pdf -outdir=$(BUILD_DIR) -auxdir=$(BUILD_DIR) $(MAIN)
	@cp $(BUILD_DIR)/slides.pdf ./slides.pdf

make_note: $(BUILD_DIR)
	$(LATEXMK) -pdf -outdir=$(BUILD_DIR) -auxdir=$(BUILD_DIR) $(NOTE_MAIN)
	@cp $(BUILD_DIR)/slides_note.pdf ./slides_note.pdf

note: make_note

clean:
	$(LATEXMK) -outdir=$(BUILD_DIR) -auxdir=$(BUILD_DIR) -c $(MAIN)
	$(LATEXMK) -outdir=$(BUILD_DIR) -auxdir=$(BUILD_DIR) -c $(NOTE_MAIN)

distclean: clean
	rm -rf $(BUILD_DIR) slides.pdf slides_note.pdf

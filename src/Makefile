.PHONY: all update clean publish

SRCS = $(wildcard *.adoc)
HTML 	:= $(patsubst %.adoc, %.html, $(SRCS))
PDF 	:= $(patsubst %.adoc, %.pdf,  $(SRCS))

all: $(HTML) $(PDF)

update:
	bundle install

clean:
	rm -rf *.err *.html *.xml *.pdf *.rxl documents/

%.html %.pdf: %.adoc
	bundle exec metanorma compile --agree-to-terms $<

publish:
	mkdir -p documents
	cp ../README.md documents/README.md
	cp ../_config.yml documents/_config.yml
	mv *.html documents/
	mv *.txt documents/

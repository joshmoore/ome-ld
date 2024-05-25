.PHONY: open
open: book
	open ../static/_build/html/core/index.html

.PHONY: book
book: docs
	jupyter-book build ../static

.PHONY: docs
docs: ../static/core/model.yaml
	cp index.md ../static/core/index.md
	gen-project ../static/core/model.yaml -d ../static/core/

validate:
	linkml-validate --legacy-mode -s ../static/core/model.yaml

../static/core/model.yaml:
	mkdir ../static/core
	./mklinkml.py ../static/core

.PHONY: clean
clean:
	rm -rf ../static/core

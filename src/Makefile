.PHONY: open
open: book
	open ../static/_build/html/core/index.html

.PHONY: book
book: docs
	jupyter-book build ../static

.PHONY: docs
docs: ../static/core/core.yaml
	gen-doc ../static/core/core.yaml -d ../static/core/ --hierarchical-class-view -vvv --log_level=DEBUG --stacktrace

../static/core/core.yaml:
	mkdir ../static/core
	./mklinkml.py ../static/core

validate:
	linkml-validate --legacy-mode -s ../static/core/core.yaml

.PHONY: clean
clean:
	rm -rf ../static/core

#
# Copyright (c) 2017, Digi International Inc.
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, you can obtain one at http://mozilla.org/MPL/2.0/.
#
# THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
# WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
# MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
# ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
# WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
# ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
# OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
#

PROGRAM := device_request_listener

CFLAGS += -Wall

CFLAGS += $(shell pkg-config --cflags cloudconnector)
LDLIBS += $(shell pkg-config --libs --static cloudconnector)

all: $(PROGRAM)

OBJS = device_request.o main.o

$(PROGRAM): $(OBJS)
	$(CC) $(LDFLAGS) $^ $(LDLIBS) -o $@

.PHONY: install
install: $(PROGRAM)
	install -d $(DESTDIR)/usr/bin
	install -m 0755 $(PROGRAM) $(DESTDIR)/usr/bin/

.PHONY: clean
clean:
	-rm -f *.o $(PROGRAM)

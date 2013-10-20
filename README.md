#CSSCV

**CSSCV is a simple, opinionated stylesheet for formatting semantic HTML to look
like a CSS file.**

## Opinionated?

CSSCV matches my own personal style of writing CSS, and uses a specific colour
scheme, [<cite>Solarized</cite>](http://ethanschoonover.com/solarized). Some of
its other more opinionated features:

* Only single classes are allowed as selectors
* It uses a BEM-style naming convention
* Rulesets are spaced by five carriage returns
* Quasi-nested rulesets are indented
* All indents are four spaces

## Enabling

CSSCV comes with the option to [en|dis]able its styling. This is so that you can
quickly and easily remove CSSCV’s unconventional look, and instead expose
unstyled HTML in case you ever need to provide a more standard format of CV to
recruiters or HR teams. Boring, but often vital. Enabling CSSCV is as simple as
adding a class of `.csscv` the the `html` element; all of CSSCV’s styles are
scoped to this namespace.

## Making stuff work

There are a series of simple yet strict rules to follow in order to use CSSCV.
Rulesets are built using definition lists and comments and selectors are usually
constructed using headings. Below is a simple example that we will deconstruct:

    <div class="ruleset">

        <h3 class="selector">Me</h3>

        <dl class="declarations">

            <dt class="property">Name</dt>
            <dd class="value"><span class="string">Harry Roberts</span></dd>

            <dt class="property">Job</dt>
            <dd class="value"><span class="string">Consultant Front-end Architect</span></dd>

            <dt class="property">Location</dt>
            <dd class="value"><span class="string">Leeds, UK</span></dd>

            <dt class="property">Skills</dt>
            <dd class="value">
                <ul class="value-list">
                    <li><span class="string">Front-end Architecture</span></li>
                    <li>Design</li>
                    <li>Development</li>
                    <li>OOCSS</li>
                    <li>Performance</li>
                    <li><span class="string">Responsive Web Design</span></li>
                    <li>Git</li>
                    <li>Vim</li>
                    <li>Agile</li>
                </ul>
            </dd>

        </dl>

    </div>

Let’s take a look at what this does:

* We wrap each ruleset in a container with a `.ruleset` class.
* The title, or _selector_, of that ruleset is a heading which carries the
  `.selector` class.
* The declarations that make up the ruleset are marked up in a `dl` which has a
  class of `.declarations`.
* Each property/value pair are marked up with `dt`s and `dd`s respectively.
  These, respectively, carry classes of `.property` and `.value`.
* Any strings that would require quoting in CSS (e.g. `"Comic Sans MS"`) can
  be wrapped in a `span` with a class of `string`. This colours them differently
  and applies opening and closing quote marks.
* Lists of values (e.g. `font-family: "Comic Sans MS", cursive;`) are marked up
  as either ordered- or unordered-lists which carry a class of `.value-list`.

As we can see, the rulesets are formed of semantic HTML elements and heavy use
of CSS pseudo-elements are used to apply CSS-like syntax (braces, (semi-)colons,
quotes, etc.

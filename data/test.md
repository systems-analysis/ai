# Heading 1 — Main Title

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent vel tortor facilisis, vulputate magna in, ornare sapien. Donec sit amet fermentum eros. Vivamus auctor purus non massa fermentum, vel tincidunt nulla bibendum. Sed euismod, urna vel aliquam lacinia, nisl nisl aliquet nisl, nec aliquam nisl nisl vel nisl. Integer malesuada bibendum diam, sit amet tincidunt odio sagittis vel.

Curabitur **pretium tincidunt** lacus. Nulla gravida orci a odio. Nullam varius, turpis et commodo pharetra, est eros bibendum elit, nec luctus magna felis sollicitudin mauris. Integer in mauris eu nibh euismod gravida. Duis ac tellus et risus vulputate vehicula. Donec lobortis risus a elit.

## Heading 2 — Section

Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.

> Etiam sit amet orci eget eros faucibus tincidunt. Duis leo. Sed fringilla mauris sit amet nibh. Donec sodales sagittis magna.
>
> — *Attribution example*

### Heading 3 — Subsection

Sed adipiscing ornare risus. Morbi est est, blandit sit amet, sagittis vel, euismod vel, velit. Pellentesque egestas sem. Suspendisse commodo ullamcorper magna. Ut nulla. Vivamus bibendum, nulla ut congue fringilla, lorem ipsum ultricies risus, ut rutrum velit tortor vel purus.

In hac habitasse platea dictumst. Morbi vestibulum volutpat enim. Proin auctor gravida sem. Ut convallis, sem sit amet interdum consectetuer, odio augue aliquam leo, nec dapibus tortor nibh sed augue. Fusce in dui non nisi egestas suscipit. Proin pretium, leo ac pellentesque mollis, felis nunc ultrices eros.

#### Heading 4 — Detail level

Nam dui ligula, fringilla a, euismod sodales, sollicitudin vel, wisi. Morbi auctor lorem non justo. Nam lacus libero, pretium at, lobortis vitae, ultricies et, tellus. Donec aliquet, tortor sed accumsan bibendum, erat ligula aliquet magna, vitae ornare odio metus a mi.

##### Heading 5 — Deep level

Nunc aliquet, augue nec adipiscing interdum, lacus tellus malesuada massa, quis varius mi purus non odio. Pellentesque condimentum, magna ut suscipit hendrerit, ipsum augue ornare nulla, non luctus diam neque sit amet urna.

###### Heading 6 — Lowest level

Cras faucibus condimentum odio. Sed ac ligula. Aliquam at eros.

---

## Text Formatting

This is **bold text**. This is *italic text*. This is ***bold italic***. This is ~~strikethrough~~. This is `inline code`. This is a [hyperlink](https://example.com "Example tooltip"). Here is a keyboard shortcut: <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>.

Superscript: E = mc<sup>2</sup>. Subscript: H<sub>2</sub>O.

## Lists

### Unordered List

- Aliquam tincidunt mauris eu risus
  - Vestibulum auctor dapibus neque
  - Nunc dignissim risus id metus
    - Cras ornare tristique elit
    - Vivamus vestibulum ntulla nec ante
- Praesent placerat risus quis eros
- Fusce pellentesque suscipit nibh

### Ordered List

1. Lorem ipsum dolor sit amet, consectetuer adipiscing elit
2. Aliquam tincidunt mauris eu risus
   1. Vestibulum auctor dapibus neque
   2. Nunc dignissim risus id metus
3. Praesent placerat risus quis eros
4. Fusce pellentesque suscipit nibh

### Task List

- [x] Write the introduction section
- [x] Add formatting examples
- [ ] Review code blocks
- [ ] Finalize the document
- [ ] Send for peer review

### Definition List

Systems Analysis
: A scientific method that uses an interdisciplinary approach to solve complex problems.

Artificial Intelligence
: The simulation of human intelligence processes by computer systems, including learning, reasoning, and self-correction.

Machine Learning
: A subset of AI that enables systems to learn and improve from experience without being explicitly programmed.

## Blockquotes

> Single-level blockquote. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

> **Nested blockquote:**
>
> > Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
> >
> > > Third level: Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.

## Code Blocks

Inline: use `console.log()` to output values.

```javascript
// JavaScript example
class SystemAnalyzer {
  constructor(name) {
    this.name = name;
    this.components = [];
  }

  addComponent(component) {
    this.components.push(component);
    return this;
  }

  analyze() {
    return this.components.map((c) => ({
      name: c.name,
      connections: c.getConnections(),
      weight: c.calculateWeight(),
    }));
  }
}

const analyzer = new SystemAnalyzer("Production Line");
analyzer.addComponent(new Component("Input")).addComponent(new Component("Process"));
console.log(analyzer.analyze());
```

```python
# Python example
from dataclasses import dataclass, field
from typing import List

@dataclass
class Component:
    name: str
    connections: List[str] = field(default_factory=list)

    def weight(self) -> float:
        return len(self.connections) * 0.5

@dataclass
class System:
    name: str
    components: List[Component] = field(default_factory=list)

    def analyze(self) -> dict:
        return {
            "system": self.name,
            "total_components": len(self.components),
            "total_weight": sum(c.weight() for c in self.components),
        }

system = System("Network", [
    Component("Router", ["Switch", "Firewall"]),
    Component("Switch", ["Router", "Server"]),
])
print(system.analyze())
```

```sql
-- SQL example
SELECT
    s.system_name,
    COUNT(c.component_id) AS total_components,
    AVG(c.weight)         AS avg_weight,
    MAX(c.updated_at)     AS last_update
FROM systems s
JOIN components c ON c.system_id = s.id
WHERE s.status = 'active'
  AND c.created_at >= '2025-01-01'
GROUP BY s.system_name
HAVING COUNT(c.component_id) > 3
ORDER BY avg_weight DESC
LIMIT 20;
```

```bash
#!/bin/bash
# Shell example
echo "Starting system check..."
for service in nginx postgres redis; do
  if systemctl is-active --quiet "$service"; then
    echo "[OK] $service is running"
  else
    echo "[FAIL] $service is not running"
    systemctl start "$service"
  fi
done
echo "Check complete."
```

## Tables

### Simple Table

| ID | Name              | Status   | Score |
|----|-------------------|----------|------:|
| 1  | Input Module      | Active   |  92.5 |
| 2  | Processing Unit   | Active   |  88.3 |
| 3  | Output Handler    | Inactive |  74.1 |
| 4  | Feedback Loop     | Active   |  95.7 |
| 5  | Control Interface | Pending  |  81.0 |

### Alignment Table

| Left-aligned | Center-aligned | Right-aligned |
|:-------------|:--------------:|--------------:|
| Lorem        |    Ipsum       |         Dolor |
| Sit          |    Amet        |   Consectetur |
| Adipiscing   |    Elit        |           Sed |

## Images

![Placeholder image](https://via.placeholder.com/600x200/1e1e1e/ffffff?text=Systems+Analysis+AI "Banner placeholder")

## Links

- [External link](https://example.com)
- [Link with title](https://example.com "Visit Example")
- [Reference-style link][ref1]
- <https://example.com> — autolink

[ref1]: https://example.com "Reference link"

## Horizontal Rules

Three variants:

---

***

___

## Footnotes

Systems analysis is a problem-solving method[^1] that applies systems thinking[^2] to decompose complex problems into manageable parts.

[^1]: First formalized in the 1950s at RAND Corporation for military strategic planning.
[^2]: Systems thinking emphasizes understanding how components interact within a whole, rather than analyzing them in isolation.

## Abbreviations

The SA methodology applies AI and ML techniques for advanced decision support in complex DSS environments.

*[SA]: Systems Analysis
*[AI]: Artificial Intelligence
*[ML]: Machine Learning
*[DSS]: Decision Support Systems

## Math (LaTeX)

Inline math: $E = mc^2$

Block math:

$$
\frac{\partial f}{\partial x} = \lim_{\Delta x \to 0} \frac{f(x + \Delta x) - f(x)}{\Delta x}
$$

## Collapsed Section

<details>
<summary>Click to expand additional details</summary>

This is hidden content that becomes visible when the user clicks the summary. Useful for long reference material, verbose logs, or supplementary information.

- Item A
- Item B
- Item C

```json
{
  "system": "Example",
  "version": "1.0.0",
  "components": 42
}
```

</details>

## Emoji (GitHub-flavored)

:rocket: :gear: :chart_with_upwards_trend: :bulb: :warning:

## Escaping

Literal characters: \*asterisks\*, \#hash\#, \[brackets\], \`backticks\`, \|pipes\|.

---

*End of document.*

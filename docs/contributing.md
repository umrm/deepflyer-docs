---
title: Contributing
---

# Contributing

DeepFlyer is open source. Contributions of any size are welcome, from fixing a typo in the docs to building a new activity.

**Repository:** (link will be updated soon)

---

=== "Report a Bug"

    1. Open the [Issues page](https://github.com/issues) on GitHub.
    2. Click **New Issue** and select **Bug Report**.
    3. Fill in the template. Include:
        - What you expected to happen
        - What actually happened
        - Which activity you were in
        - Your browser name and version

=== "Improve the Docs"

    All documentation lives in the `docs/` folder. Every page is a Markdown file.

    1. Fork the repository on GitHub.
    2. Edit or add `.md` files in `docs/`.
    3. Run `mkdocs serve` locally to preview your changes.
    4. Open a pull request against the `main` branch.

    **Adding a new page:**

    1. Create `docs/your-section/your-page.md`
    2. Add the page to the `nav:` section in `mkdocs.yml`
    3. Link to it from at least one existing page

=== "Code Contributions"

   <div class="inprogress-box">
      <span class="icon">🚧</span>
      <h3>Being Written</h3>
    </div>

=== "New Activities"

    Open a [Feature Request issue](https://github.com/issues) first to discuss the design before implementing.

    A new activity needs:

    | What to build | Where it goes |
    |---|---|
    | Frontend page | `frontend/src/pages/activities/YourActivity.tsx` |
    | Route registration | `frontend/src/App.tsx` |
    | Backend session config | `shared-backend/main.py` inside ACTIVITY_CONFIG |
    | ROS 2 node (if needed) | `sim-container/your_node.py` |
    | Documentation page | `docs/activities/your-activity.md` |
    | Entry in activities list | `docs/activities/index.md` |

---

## Licence

DeepFlyer is released under the **MIT Licence**. By contributing, you agree your work will be licensed under the same terms.

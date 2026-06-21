# GitHub web update steps

Use this package to clean the repository structure so the diagrams folder contains only PNG and draw.io files.

## Recommended update

1. Open the repository on GitHub:
   `ErwinaChmiel/clinic-appointment-system-uml-ba-case`

2. Delete the old `diagrams` folder from the repository.

3. Upload the new `diagrams` folder from this package.

4. Replace the root `README.md` with the `README.md` from this package.

5. Commit message:

```text
Replace diagrams with bilingual PNG and drawio structure
```

## Final structure

```text
README.md
diagrams/
├── README.md
├── png/
│   ├── pl/
│   └── en/
└── drawio/
    ├── pl/
    └── en/
```

Do not upload old `svg`, `mermaid` or `plantuml` folders if you want the diagrams folder to contain only PNG and draw.io files.

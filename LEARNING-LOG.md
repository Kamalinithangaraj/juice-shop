\# DevSecOps Learning Log



\## Week 1: CI/CD Fundamentals



\### What I built

\- Forked and ran OWASP Juice Shop locally

\- Created a GitHub Actions workflow (hello.yml) to learn basic YAML syntax

\- Built a real CI pipeline (basic-ci.yml) that checks out code, sets up Node.js,

&#x20; installs dependencies, and runs lint on every push/PR to master



\### What I learned

\- How GitHub Actions triggers, jobs, and steps work

\- How to read and diagnose a failed CI run (file, line number, rule name, exit code)

\- A linter only checks code style, not security. I proved this by adding a

&#x20; hardcoded secret (`const debugPassword = 'hardcoded123'`) to the code.

&#x20; Lint failed at first only because the variable was "unused" - once I used it

&#x20; in a console.log, lint passed cleanly even though the hardcoded secret was

&#x20; still sitting in the code. This showed me why DevSecOps pipelines need

&#x20; dedicated security tools, not just a linter.



\### What's next (Week 2)

\- Add Semgrep (SAST) to this same pipeline to catch insecure code patterns

\- Use the debugPassword line as a live example of something Semgrep/a secrets

&#x20; scanner should catch that lint missed


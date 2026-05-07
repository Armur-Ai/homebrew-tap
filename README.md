# homebrew-tap

Homebrew tap for [Pentest Swarm AI](https://github.com/Armur-Ai/Pentest-Swarm-AI) — open-source autonomous pentesting via a stigmergic swarm of AI agents.

## Install

```bash
brew install Armur-Ai/tap/pentestswarm
```

That's it. First run:

```bash
pentestswarm init        # one-shot setup (paste your Claude API key)
pentestswarm scan example.com
```

## What's in the swarm

The `pentestswarm` binary orchestrates a stigmergic swarm of agents (recon, classifier, exploit, report) coordinating through a shared blackboard, not through a central planner.

The swarm calls out to standard offensive-security tools when they're available:

```
nmap     subfinder    httpx     nuclei     ffuf       sqlmap
amass    dnsx         naabu     katana     gau        gobuster
gowitness  trufflehog  gitleaks  semgrep
```

Install only what you need; missing tools are detected and gracefully skipped. Or skip the host install entirely and run the bundled Docker image where all 16 are pre-installed:

```bash
docker run --rm -e PENTESTSWARM_ORCHESTRATOR_API_KEY=$KEY \
  ghcr.io/armur-ai/pentestswarm:edge scan example.com
```

## Updates

This formula is rewritten by the upstream release workflow whenever a new version of Pentest Swarm AI is tagged, so:

```bash
brew update
brew upgrade pentestswarm
```

…always tracks the latest release.

## License

The formula in this repository is licensed under Apache-2.0, matching upstream.

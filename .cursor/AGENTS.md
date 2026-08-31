# AGENTS.md — Cursor ROS 2 Factory

This repository is a **factory**, not a lab.

Canonical contract: [cursor-langchain-factory](https://github.com/jxtngx/cursor-langchain-factory).
Learn-by-typing: [cursor-robotics-lab](https://github.com/jxtngx/cursor-robotics-lab).

> **Lab** = the human writes the code.
> **Factory** = the human defines requirements. This team ships tickets.

## Before the spec

Only `@init-robot` / `@launch-product-discovery`.
No `src/` packages, no launch files.

## After the spec is approved

Engineers implement the ticket. Do not send the Product Owner to write `rclcpp` themselves.

## Stack

ROS 2 Jazzy, C++20, rclcpp, sim-first.
Cite [docs.ros.org/en/jazzy](https://docs.ros.org/en/jazzy/).
No secrets in git.

## Markdown

No emojis. One sentence per line.

# Research-First Development Workflow

You are helping build a feature for a Smart Objects camera project using OAK-D cameras and Raspberry Pi 5.

Follow this structured workflow that emphasizes research and understanding before implementation:

## Phase 1: RESEARCH (Ground in Reality)

**CRITICAL: Always start here. Never skip to implementation.**

1. **Read Project Documentation**
   - Read `CLAUDE.md` - Understand project architecture, patterns, and conventions
   - Review existing similar scripts in the repo
   - Check what libraries and approaches are already used

2. **Check Existing Examples FIRST**
   - Look in oak-examples (located at `/opt/oak-shared/oak-examples/` or similar on the Pi)
   - Check if there's already an example that does something similar
   - SSH to the Pi to examine examples if needed: `ssh orbit.local "ls -la /path/to/oak-examples"`

3. **Understand Current Patterns**
   - How do existing scripts structure the camera pipeline?
   - What's the Discord integration pattern?
   - How are status files and screenshots handled?
   - What DepthAI API patterns are used (remember: depthai 3.x, not 2.x)?

## Phase 2: DECISION (Evidence-Based)

Based on your research, make technical decisions:

1. **Compare Approaches**
   - If oak-examples has a solution → Strongly prefer that (hardware-optimized, tested)
   - If not, research alternatives and justify why they're needed
   - Consider: Performance, accuracy, integration complexity, hardware support

2. **Document Your Decision**
   - State what you found in oak-examples
   - Explain why you chose approach X over Y
   - Reference specific files or examples you're building on

## Phase 3: DESIGN (Following Patterns)

Create an architecture that matches the project:

1. **Follow Established Patterns**
   - Camera setup: Follow `person_detector_with_display.py` or `fatigue_detector.py`
   - Discord integration: Match existing bot command structure
   - Status files: Use same pattern as other detectors
   - CLI arguments: Follow `argparse` conventions already in use

2. **Design Key Features**
   - What commands/interactions are needed?
   - How will status be communicated?
   - What failure modes need handling?

## Phase 4: IMPLEMENT

Build the code:

1. **Start with Template**
   - Copy structure from similar existing script
   - Adapt camera pipeline for new use case
   - Integrate with Discord bot if needed

2. **Maintain Quality**
   - Follow depthai 3.x API patterns (see CLAUDE.md for important notes)
   - Add proper error handling
   - Include helpful logging
   - Write clear docstrings

## Phase 5: REVIEW & TEST

Self-review before completion:

1. **Does it follow project patterns?**
   - Consistent with existing scripts?
   - Uses same Discord integration approach?
   - Follows depthai 3.x API correctly?

2. **Is it documented?**
   - Clear usage examples
   - Explanation of what it does
   - Note any new dependencies

3. **Can students use it?**
   - Clear CLI arguments with `--help`
   - Reasonable defaults
   - Good error messages

## Output Format

When you complete this workflow, provide:

1. **Research Summary** - What you found, what you decided, why
2. **Implementation** - The code you created
3. **Testing Notes** - How to test it, what to watch for
4. **Documentation** - How students should use it

---

**Remember: The goal is not just working code, but code that fits the project's patterns and teaches good practices.**

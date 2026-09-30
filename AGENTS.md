# pyroscope-python fork of dd-trace-py

Consumed as a git submodule by grafana/pyroscope-python. Base: upstream tag `v4.11.1`.
Original upstream history is kept. Two commits on top: a prune commit and one patch commit.

## Keep (upstream paths unchanged)

- `ddtrace/profiling/` (python, pyx, pxd, pyi, `_memalloc*` and `_pymacro.h` C++)
- `ddtrace/internal/datadog/profiling/` (stack, echion, dd_wrapper, ddup, profiling_helpers, cmake, python helpers), including `test/` and `fuzz/`
- `tests/profiling/`, `tests/commands/ddtrace_run_profiling.py`, `scripts/profiles/`, `ddtrace/internal/settings/profiling.py*`
- `ddtrace/internal/wrapping/`, `module.py`, `forksafe.py`, `_unpatched.py`, `logger.py`, `_threads.*`
- `LICENSE*`, `NOTICE`
- Pyroscope build files at the repo root: `CMakeLists.txt`, `BundleStaticLibrary.cmake`, `pyroscope/Pyroscope.h`

Kept tests and fuzzers are never built or run from this repo.

## Remove

Everything else: `.github/`, `.gitlab*`, `.circleci`, `.claude/`, `.cursor/`, `.riot/`, tests, docs, benchmarks, other products, packaging.
No CI or workflows of any kind belong in this repo.

## Patches

Files carrying `// Pyroscope patch:` markers: `_memalloc.cpp`, `_memalloc_heap.{cpp,h}`, `_memalloc_tb.{cpp,h}`.
Keep patches in a single commit on top of the base.

## Updating from upstream

Merge or rebase onto the new upstream tag, then re-apply the keep and remove rules above and re-check the patched files.

cmake_minimum_required(VERSION 3.0)
project(kissat C)

file(WRITE ${CMAKE_CURRENT_BINARY_DIR}/generated/build.h
  "#define VERSION \"\"\n"
  "#define COMPILER \"\"\n"
  "#define ID \"\"\n"
  "#define BUILD \"\"\n"
  "#define DIR \"\"\n"
)

include_directories(${CMAKE_CURRENT_BINARY_DIR}/generated)

set(CMAKE_C_FLAGS "-W -Wall -O3 -DNEMBEDDED -DNDEBUG -DNMETRICS -DNSTATISTICS")

add_library(kissat STATIC
  src/allocate.c
  src/analyze.c
  src/ands.c
  # src/application.c
  src/arena.c
  src/assign.c
  src/autarky.c
  src/averages.c
  src/backtrack.c
  src/backward.c
  src/build.c
  src/bump.c
  src/check.c
  src/clause.c
  src/clueue.c
  src/collect.c
  src/colors.c
  src/compact.c
  src/config.c
  src/decide.c
  src/deduce.c
  src/dense.c
  src/dominate.c
  src/dump.c
  src/eliminate.c
  src/equivalences.c
  src/error.c
  src/extend.c
  src/failed.c
  src/file.c
  src/flags.c
  src/format.c
  src/forward.c
  src/frames.c
  src/gates.c
  src/handle.c
  src/heap.c
  src/ifthenelse.c
  src/import.c
  src/internal.c
  src/learn.c
  src/limits.c
  src/logging.c
  # src/main.c
  src/minimize.c
  src/mode.c
  src/options.c
  # src/parse.c
  src/phases.c
  src/print.c
  src/probe.c
  src/profile.c
  src/promote.c
  src/proof.c
  src/propdense.c
  src/prophyper.c
  src/proprobe.c
  src/propsearch.c
  src/queue.c
  src/reduce.c
  src/reluctant.c
  src/rephase.c
  src/report.c
  src/resize.c
  src/resolve.c
  src/resources.c
  src/restart.c
  src/search.c
  src/smooth.c
  src/sort.c
  src/stack.c
  src/statistics.c
  src/strengthen.c
  src/substitute.c
  src/terminate.c
  src/ternary.c
  src/trail.c
  src/transitive.c
  src/utilities.c
  src/vector.c
  src/vivify.c
  src/walk.c
  src/watch.c
  src/weaken.c
  # src/witness.c
  src/xors.c
)

set_target_properties(kissat PROPERTIES PUBLIC_HEADER src/kissat.h)
install(TARGETS kissat)

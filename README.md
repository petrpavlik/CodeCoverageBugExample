# CodeCoverageBugExample

run

```
xcodebuild "-workspace" "CodeCoverageBugExample.xcworkspace" "-scheme" "CodeCoverageBugExample" "build" "COMPILER_INDEX_STORE_ENABLE=NO" "test" "-destination" "id=2E465F79-A48A-4C32-BBE0-F1104A27E4C7" "-resultBundlePath" "Test.xcresult" "GCC_INSTRUMENT_PROGRAM_FLOW_ARCS=YES" "GCC_GENERATE_TEST_COVERAGE_FILES=YES"
```

to experience the bug

```
duplicate symbol '___gcov_flush' in:
    /Users/petr/Library/Developer/Xcode/DerivedData/CodeCoverageBugExample-gictjvuwzgnjolaocdbqaotvidpx/Build/Products/Debug-iphonesimulator/SDWebImage.o
    /Users/petr/Library/Developer/Xcode/DerivedData/CodeCoverageBugExample-gictjvuwzgnjolaocdbqaotvidpx/Build/Products/Debug-iphonesimulator/CocoaAsyncSocket.o
ld: 1 duplicate symbol for architecture x86_64
clang: error: linker command failed with exit code 1 (use -v to see invocation)
```

You need to delete `Test.xcresult` before launching the command again

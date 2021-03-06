## Requirement

Recent versions of

- curl
- jq

Only tested on Mac.

## Usage

```
Usage: stress-test $sub_command $args

Subcommands:
  run $repo $sha $num_of_builds
  run-keep $repo $sha $num_of_builds_to_keep_running
  cancel $repo
```

## Example

Kick N builds and exit

```
bash-4.4$ ./stress-test run kimh/picard-test 502a881f 3
Start stress testing at 20170209-17-34-47
Running: https://circleci.com/gh/kimh/picard-test/545
Running: https://circleci.com/gh/kimh/picard-test/546
Running: https://circleci.com/gh/kimh/picard-test/547
```

Keep running N builds

```
bash-4.4$ ./stress-test run-keep kimh/picard-test 502a881f 3
Start stress test
Running: https://circleci.com/gh/kimh/picard-test/483
Running: https://circleci.com/gh/kimh/picard-test/484
Running: https://circleci.com/gh/kimh/picard-test/485
.....................
Running: https://circleci.com/gh/kimh/picard-test/486
Running: https://circleci.com/gh/kimh/picard-test/487
Running: https://circleci.com/gh/kimh/picard-test/488
.....
```

Cancelling all stress testing builds that are either queued or running

```
bash-4.4$ ./stress-test cancel kimh/picard-test
Successfully canceled: https://circleci.com/gh/kimh/picard-test/488
Successfully canceled: https://circleci.com/gh/kimh/picard-test/487
Successfully canceled: https://circleci.com/gh/kimh/picard-test/486
```

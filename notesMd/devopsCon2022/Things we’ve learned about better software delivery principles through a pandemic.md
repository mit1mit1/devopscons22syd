## Things we’ve learned about better software delivery principles through a pandemic - Jeremy Meiss, Director of DevRel and Community at CircleCi

Software delivery was never more business critical than now. Solutions are expected to be beautiful, powerful and intuitive. There is a rapid pace of change and growing complexities. How can a company succeed and also beat the competition?

Jeremy is here from the states, followable from Twitter at IAmJerdog.

The data in this talk will be from CircleCi reports (based on metrics of actual engineering work), and also from the important State of DevOps report (based on a survey).

Circle CI have done a pre-pandemic, mid-pandemic, and post-pandemic survey, the last of which was huge.

One size doesn't fit all - you are not Netflix, unless you are, so you don't need to do the same stuff as Netflix. Benchmarks are use-dependent.

## Four CI/CD benchmarks

- Throughput (merge on all Pr, should be many deploys per day)
- Duration
- Mean time to recovery
- Success rate

By CircleCI metrics, teams seem to be improving.

## Throughput

Make smaller commits more often (as long as they still include meaningful functionality).

The exact number has to be dependent on your team. Good automated testing unblocks you from manual testing. A fully automated pipeline allows you to up throughput.

Mid- and post-pandemic, weekend and out of hours pipeline runs became more frequent.

Still, most teams are not deploying dozens of times per day. Or, they might be deploying dozens of times a day for one primary repo, but not for the others. Continuous validation is the real goal.

Its valuable for the org to see changes and progress week by week.

Takeaway: prioritise lean agile development.

## Duration

Duration is the length of time it takes a workflow to run. It hamstrings or unlocks everything else.

You need to fail fast, with good info.

(Interestingly, 5% of builds failed in less than 12 seconds. Could be unit tests, pushing a small pre built artifact - or a bad pipeline config file).

More rigorous CI does increase the time. There was a ramp up in average duration as the pandemic started, and they've linked it to more automated testing - this is good and needed.

A 30 minute run is the 95 percentile, a decent sweet spot still where you can cover everything but it the duration isn't awful.

CircleCI notices that default branches run more quickly than feature branch across the board.

Ways to improve this metric:

- Use test splitting so you can run tests in parallel.
- Use docker images specific for CI (you don't need a full Ubuntu image to build ruby)
- Cache strategies (for npm modules, etc).
- Use optimal machine size (a low memory machine running big build job is going to run slower and ultimately cost the same or more than a quick beefy machine)

## Mean time to recovery

The lower bound for mean time to recovery is duration run time. You've got to run a build to fix the break.

Brandon Byers suggests the first fix for a red commit is to revert it and run CI - this should be the easiest and most guaranteed fix.

Data on recovery time - 5% of recoveries were in minutes, 50% were in an hour or two. But the mean recovery time across the board is in 14 hours, implying breaking code changes are pushed and then people go home.

90th and 95th percentile are people pushing then going home for the weekend. Of course, this data includes Dev branches, so maybe it's okay. No problem with an investigation branch staying broken over the weekend. Mean time to recovery across the board peaks at end of year holiday time too.

## Success rate

Success rate on default branches is sitting pretty at almost 70%.

Default branches should have high success rates - it should be fine that feature branches do not. If your company cares about the success rate of your feature branches, something is wrong.

Low success rates on default implies your tests are inadequate.

## Who needs what

Throughput is very company specific - big companies should have higher throughput than small ones, etc. However, the benchmarks for mean time to recovery, duration and success rate should be good for everyone to hit.

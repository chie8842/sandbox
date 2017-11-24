stackprof
========-
a sampling call-stack profiler for ruby 2.1+

```
$ stackprof tmp/stackprof-cpu-*.dump --text --limit 1
  ==================================
    Mode: cpu(1000)
    Samples: 60395 (1.09% miss rate)
    GC: 2851 (4.72%)
  ==================================
       TOTAL    (pct)     SAMPLES    (pct)     FRAME
        1660   (2.7%)        1595   (2.6%)     String#blank?

$ stackprof tmp/stackprof-cpu-*.dump --method 'String#blank?'
  String#blank? (gems/activesupport-2.3.14.github30/lib/active_support/core_ext/object/blank.rb:80)
    samples:  1595 self (2.6%)  /   1660 total (2.7%)
    callers:
       373  (   41.0%)  ApplicationHelper#current_user
       192  (   21.1%)  ApplicationHelper#current_repository
    callers:
       803  (   48.4%)  Object#present?
    code:
                                    |    80  |   def blank?
   1225    (2.0%) /  1225   (2.0%)  |    81  |     self !~ /[^[:space:]]/
                                    |    82  |   end

$ stackprof tmp/stackprof-cpu-*.dump --method 'Object#present?'
  Object#present? (gems/activesupport-2.3.14.github30/lib/active_support/core_ext/object/blank.rb:20)
    samples:    59 self (0.1%)  /    910 total (1.5%)
    callees (851 total):
       803  (   94.4%)  String#blank?
        32  (    3.8%)  Object#blank?
        16  (    1.9%)  NilClass#blank?
    code:
                                    |    20  |   def present?
    910    (1.5%) /    59   (0.1%)  |    21  |     !blank?
                                    |    22  |   end
```

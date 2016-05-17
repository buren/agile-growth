```ruby
include Wroclaw

author = Presenter.new(:buren)
slides = AgileGrowth::Slides.new

wait until author.ready?

author.present(slides) do |slide|
  print slide
  any_questions? if slide.last?
end
```

_Goto_: http://jacobburenstam.com/agile-growth

<img class="natural-image" src="images/logo-inv.svg" style="max-width:400px">

---

# GOTO

## [jacobburenstam.com/agile-growth](http://jacobburenstam.com/agile-growth)

---

<div data-poller="js-poll-developer">
  <p>Developer?</p>
  <button data-answer>Neckbeard</button>
  <button data-answer>Ninja</button>
  <button data-answer>OK</button>
  <button data-answer>Not so much</button>
  <button data-answer>Developer?</button>
  <hr>
  <div data-chart data-refresh="5"></div>
</div>

---

<div data-poller="js-native-wroclaw">
  <p>Wroclaw native?</p>
  <button data-answer>Born and raised</button>
  <button data-answer>+5 years</button>
  <button data-answer>2-5</button>
  <button data-answer>0-2</button>
  <button data-answer>Don't live here</button>
  <hr>
  <div data-chart data-refresh="5"></div>
</div>

---

## Agenda

* Talk....... :zzz:
* Please interupt me!

---

### Disclaimer

* __Personal__ opinions, __not__ the opinions of my employer.
* YMMV (Your mileage may vary)

---

## Jacob Burenstam

* Open source tinkerer
* Useless code enthusiast
* Work @ Young/Skilled

<hr>

* [github.com/buren](https://github.com/buren)
* [keybase.io/buren](https://keybase.io/buren)

---

# Growth

:chart_with_upwards_trend: :zap: :tada: :star: :metal: :money_with_wings:

__or__

:chart_with_downwards_trend: :pill: :hocho: :gun: :bomb:

---

Remember the code from the first slide?

```ruby
include Wroclaw

author = Presenter.new(:buren)
slides = AgileGrowth::Slides.new

wait until author.ready?

author.present(slides) do |slide|
  print slide
  any_questions? if slide.last?
end
```

---

```ruby
DEADLINE = Time.new(2016, 5, 18, 19, 0, 0).freeze
module Wroclaw;end
module Wroclaw::AgileGrowth;end
String.class_eval { define_method(:last?) { false } }
NilClass.class_eval { define_method(:last?) { true } }
define_method(:wait) { puts 'Still not ready..';sleep 3 }
define_method(:any_questions?) { puts 'Any questions?' }
define_method(:feedback) { puts 'Feedback?' }
class Wroclaw::Presenter < Struct.new(:name)
  define_method(:ready?) { Time.now >= DEADLINE }
  def present(slides); slides.to_a.each { |slide| yield(slide) };end
end
class Wroclaw::AgileGrowth::Slides
  define_method(:initialize) { @slides = File.read('slides.md').split('---') }
  define_method(:to_a) { @slides + [nil] }
end
```

This actually makes the previous code work :trollface:

---

* [http://git.io/vnWsf](http://git.io/vnWsf)

<img src="images/github-mark.png" alt="GitHub logo" class="octocat">

---

# Questions?

## github.com/buren
## keybase.io/buren

<img class="natural-image" src="images/logo-inv.svg" style="max-width: 300px;"/>

---

<img class="natural-image" src="images/logo-inv.svg"/>

<!-- Third party dependencies -->
<script src="js/libs/jquery.js"></script>
<!-- <script src="js/libs/highcharts.js"></script> -->
<script src="https://www.google.com/jsapi"></script>
<script src="js/libs/chartkick.js"></script>

<!-- JavaScript -->
<script src="js/log.js"></script>
<script src="js/resize-hack.js"></script>

<script>
  PollerConfig = { url: 'https://throwawaypoll.herokuapp.com' };
</script>
<script src="js/poller.js"></script>
<script src="js/poller-dom.js"></script>
<script>
  PollerConfig = { url: 'https://throwawaypoll.herokuapp.com' };
</script>

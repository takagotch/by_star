### by_star
---

https://github.com/radar/by_star

```ruby
Post.by_year(2018)
Post.before(Date.today)
Post.yesterday
Post.between_times(Time.zone.now - 3.hours,
                   Time.zone.now)
@post.next

class MyModel
  include Mongoid::Dcoument
  include Mongoid::ByStar

Post.by_month("January", field: :updated_at)

class Post < ActiveRecord::Base
  by_star_field :updated_at
end

Post.by_month.your_scope
Post.by_month(1).include(:tags).where("tags.name" => "ruby")

Post.by_month.count
Post.by_day('2018-10-11', offset: 9.hours)

class Post < ActiveRecord::Base
  by_star_field offset: 9.hours
end

by_star_field :start_time, :end_time

MultiDayEvent.by_month("January")

MultiDayEvent.by_month("January", :strict => true)

Post.between_times(time1, time2)
Post.between_times(time1..time2)
Post.between_times(date1, date2)
Post.before
Post.after
Post.before(Date.today + 2)
Post.after(Time.now + 5.days)

Post.before("next tuesday")

Post.last.previous
Post.first.next

Post.last.previous(field: "published_at")
Post.first.next(field: "published_at")

Post.by_year
Post.by_year(09)
Post.by_year(2000)
Post.by_year(1999)

Post.by_month(1)
Post.by_month("January")

Post.by_month(1, year: 2007)
Post.by_month("January", year: 2007)
Post.by_month(Time.local(2012, 11, 24))
Post.by_month(Time.local(2012, 11, 24))
Post.by_calendar_month
Post.by_fortnight
Post.by_fortnight(18)
Post.by_fortnight(18, year: 2012)
Post.by_fortnight(Time.local(2012,1,1))

Post.by_week
Post.by_cweek
Post.by_week(36)
Post.by_cweek
Post.by_week(36)
Post.by_cweek(37)
Post.by_week(36, year: 2012)
Post.by_cweek(37, year: 2012)
Post.by_week(Time.local(2012,1,1))
Post.by_cweek(Time.local(2012,1,1))

Post.by_weekend(Time.now)
Post.by_day
Post.today
Post.by_day(Time.local(2012, 1, 1))
Post.by_day("next tuesday")
Post.by_quarter
Post.by_quarter(4)
Post.by_quarter(4)
Post.by_quarter(2, year: 2012)
Post.by_week(Time.local(2012,1,1))

ACTIVE_RECORD_VERSION=4.0.0 MONGOID_VERSION=master bundle update
ACTIVE_RECORD_VERSION=4.0.0 MONGOID_VERSION=master bundle exec rspec spec

```

```
gem 'by_star', git: "git://github.com/radar/by_star"
bundle install

```


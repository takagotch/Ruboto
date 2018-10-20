### Ruboto
---

https://github.com/ruboto/ruboto

http://ruboto.org/

```
gem install ruboto

git clone https://github.com/ruboto/ruboto.git
cd ruboto
rake install

ruboto setup -v
ruboto emulator -t android-17
ruboto gen app --package.com.yourdomain.whatever
ruboto gen app --package.com.yourdomain.whatever --path path/to/where/you/want/the/app --name NameOfApp --target android-version --min-sdk another-android-version --activity MainActivityName
ruboto gen class ClasName --name YourObjectName
ruboto gen class BroadcastReceiver --name AwesomenessReceiver

rake debug
rake install
rake start
rake install start
rake release
rake update_scripts
rake update_scripts:restart

rake test
cd test ; ant run-tests

ruboto emulator
ruboto emulator -t 17

```

```ruby
class FooActivity
  def onCreate(bundle)
    super
    android.util.Log.v 'MYAPPNAME', 'onCreate got called!'
  end
  def onPause
   super
   android.util.Log.v 'MYAPPNAME', 'onPause got called!'
  end
end

activity Java::org.ruboto.sample_app.RubotoSampleAppActivity
setup do |activity|
  start = Time.now
  loop do
    @text_view = activity.findViewById(43)
    break if @text_view || (Time.now - start > 60)
    sleep 1
  end
  assert @text_view
end
test('initial setup') do |activity|
  assert_equal "What hath Matz wrought?", @text_view.text
end
test('button changes text') do |activity|
  button = activity.findViewById(43)
  button.performClick
  assert_equal "What hath Matz wrought!", @text_view.text
end

alias ics="ruboto emulator -t 15"
alias jellyb="ruboto emulator -t 16"
alias jb17="ruboto emulator -t 17"
```


```
```


---
layout: post
title: "libxml2 and failing capybara tests"
date: 2013-07-29 23:04
comments: true
categories: 
- ruby
- rails
- nokogiri
- libxml2
---

Checkout a repo, brand new gemset, run the test suite which for sure is running green on 
at least 3 of your colleagues machines and **Boom!** the tests are not passing on yours!

And there it starts the infinite debugging.

One of the Cucumber tests not passing had a css selector like the following:
```ruby
Then /^I can edit something$/ do
  within("#something tr td:nth-child(2)") do
    click_link "Edit"
  end

  # [...]

end
```
which had nothing strange in it; plus I could actually see in the browser, using *save_and_open_page* 
that the elements that Capybara was supposed to select, were actually there.

### WTF THEN?!?

After some time shooting in the dark, reinstalling and banging the head against the desk, I figured that the
problem should have been related to some system library I was using and it turned out I was right.

Capybara has a wrapper around our friend **Nokogiri** that wraps **libxml2** and the only difference between
my machine and my colleagues ones could have been exactly the version of *libxml2*.
To prove the theory at that point, I just had to install and older version of libxml2 and reinstall nokogiri
before running the test suite again:
```bash
~> brew versions libxml2                    
2.9.1    git checkout 31caa27 /usr/local/Library/Formula/libxml2.rb
2.9.0    git checkout 5dd45d7 /usr/local/Library/Formula/libxml2.rb
2.8.0    git checkout 763d946 /usr/local/Library/Formula/libxml2.rb
2.7.8    git checkout 497b13a /usr/local/Library/Formula/libxml2.rb
2.7.7    git checkout f4a925d /usr/local/Library/Formula/libxml2.rb
2.7.6    git checkout 8939a91 /usr/local/Library/Formula/libxml2.rb
~> brew tap homebrew/versions
~> cd /usr/local
~> git checkout 497b13a /usr/local/Library/Formula/libxml2.rb
~> brew install libxml2
~> brew link --force libxml2
```
and libxslt:
```bash
~> brew versions libxslt                                  
1.1.28   git checkout 98d5e91 Library/Formula/libxslt.rb
1.1.26   git checkout 2053036 Library/Formula/libxslt.rb
~> git checkout 2053036 Library/Formula/libxslt.rb
~> brew install libxslt
~> brew link --force libxslt
```
then nokogiri:
```bash
~> gem uninstall nokogiri
~> gem install nokogiri
```
That was it! Tests running, all green! **F@#k YEAH!**

Now surely we can update the test suite to work with the latest *libxml2* :P

Happy coding.

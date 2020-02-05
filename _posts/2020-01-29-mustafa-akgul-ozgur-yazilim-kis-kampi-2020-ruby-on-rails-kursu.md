---
layout: post
title: Mustafa Akgül Özgür Yazılım Kış Kampı 2020 Ruby on Rails Kursu
---

25-28 Ocak Tarihlerinde Anadolu Üniversitesinde düzenlenen **Ruby on Rails** kursunda aldığım ders notlarım. 

## 1. Gün

Ruby syle guide

Revolation OS izle.

### Gitflow

https://nvie.com/posts/a-successful-git-branching-model/

<hr>

Iaas

Paas

Saas

<hr>

https://puma.io/

https://github.com/puma/puma

<hr>

## Ruby Gem

Rubynin hazine sandığıdır. Icinde ruby, python, js vb kodlar olabilir.

TODO: Ruby Gem githubdan bak.

katip gemi lab2023 bak.

https://github.com/lab2023/katip

Ruby Gems

https://rubygems.org/

Gemler private repository olabiliyor.
<hr>


# My First Gem


## bundle init


```
bundle init

```
Yukarıdaki kod Gemfile oluşturur.

```
# frozen_string_literal: true

source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"
```

`{|repo_name| "https://github.com/#{repo_name}" }` github urlsi değişebilir. Gitlab olabilir. Ama private olursa herkesin ulaşabilmesi için izin verilmesi gerekir.


## bundle install

```
bundle install
```


```
GEM
  remote: https://rubygems.org/
  specs:

PLATFORMS
  ruby

DEPENDENCIES

BUNDLED WITH
   2.1.4


```

# 1. Gün Özeti

Http, Web Servisler Https vb çalışma mantığını öğrendik.

Git ve Gitflow öğrendik.

Gem öğrendik.

Gem ile proje geliştirmeyi öğrendik.

Gem: bundle, bundle insert vb öğrendik.
<hr>

## 2. Gün

## Ruby Toolbox

Gems Popularity, Releases, Activity gibi istatistikleri gösteriyor. Gem bulmak için kullanılıyor.

https://www.ruby-toolbox.com/

### Devise Gem

https://github.com/heartcombo/devise

## Rails Doctrine

#### En az süpriz ilkesi

Python exit-quit örneği

Inflection Kütüphanesi

### data query language ve Data definition language

<hr>

## 3. Gün

https://stimulusjs.org/

https://kebab-project.com/

### Dom ve Bom


* Dom: Document Object Model

(document. , browser. gibi)

* BOM: Browser Object Model

(navigator. ,window.Open)

* ECMAScript 6

Event-driven programming

TODO: mdm bak.

TODO - Oku: https://stimulusjs.org/handbook/origin

TODO - Oku: https://m.signalvnoise.com/the-majestic-monolith/

transaction araştır

https://guides.rubyonrails.org/active_record_basics.html

https://docs.rollbar.com/docs/rails

https://gist.github.com/peternixey/1978249

Rails Admin: https://activeadmin.info/

<hr>

## 4. Gün

jbuilder

https://github.com/rails/jbuilder

### content_for == Jinja Templates
```html
<% content_for :head do %>
  <title>A simple page</title>
<% end %>
```



https://guides.rubyonrails.org/

layouts_and_rendering.html#using-the-content-for-method

* default_url_sections

https://guides.rubyonrails.org/action_controller_overview.html#default-url-options

* Sessions

https://guides.rubyonrails.org/action_controller_overview.html#session

<hr>
* Mail

https://mailtrap.io/

https://guides.rubyonrails.org/action_mailer_basics.html

Maillarda **path** değil **url** kullanılır. `gmail.com/path` olmaması için.

**deliver_now** şu an gönderilir.

### Active Job

Notification vb iş yazma

https://guides.rubyonrails.org/active_job_basics.html

```ruby
# Enqueue a job to be performed 1 week from now.
GuestsCleanupJob.set(wait: 1.week).perform_later(guest)
```

Redis ve Sidekiq öneriliyor.

https://github.com/ondrejbartas/sidekiq-cron



https://crontab.guru/


### Active Storage

Dosya kaydetme okuma vb. için kullanılır.

#### Database ve migrate işlemleri

https://guides.rubyonrails.org/active_storage_overview.html

```
rails active_storage:install
```

```
rails db:migrate
```
Image crop resize vb için **Minimagick Gem**

https://github.com/minimagick/minimagick

* Direct Uploads uploadlanırken progressbar çıkıyor.

#### Ckeditor == trix

https://edgeguides.rubyonrails.org/action_text_overview.html

https://github.com/basecamp/trix 

#### Action Cable 

soket

* Language control için routes


```
scope "/:locale" do
```

## Ruby Gems

bml

simple_form

resque

friendly_id

bullet


https://www.railscasts.com


rails book'u 4. versyonu bul oku

gorails.com

https://thoughtbot.com/upcase

https://github.com/lab2023/cybele

https://capistranorb.com/

https://lab2023.com/ruby-on-rails-uygulamasinin-heroku-servisinde-coklu-ortamda-yayinlanmasi.html

dokku heroku 

https://rubyturkiye.org/
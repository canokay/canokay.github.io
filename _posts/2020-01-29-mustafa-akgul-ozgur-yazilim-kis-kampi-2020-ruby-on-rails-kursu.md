---
layout: post
title: Mustafa Akgül Özgür Yazılım Kış Kampı 2020 Ruby on Rails Kursu
---

25-28 Ocak Tarihlerinde Anadolu Üniversitesinde düzenlenen **Ruby on Rails** kursunda aldığım ders notlarım. 

## 1. Gün

* Ruby syle guide

* Revolation OS izle.

### Gitflow

* <a href="https://nvie.com/posts/a-successful-git-branching-model/">https://nvie.com/posts/a-successful-git-branching-model/</a>


<hr>

* Iaas

* Paas

* Saas

<hr>

* <a href="https://puma.io/">https://puma.io/</a>

* <a href="https://github.com/puma/puma">https://github.com/puma/puma</a>

<hr>

## Ruby Gem

Rubynin hazine sandığıdır. Icinde ruby, python, js vb kodlar olabilir.

TODO: Ruby Gem githubdan bak.

TODO: katip gemi lab2023 bak.

* <a href="https://github.com/lab2023/katip">https://github.com/lab2023/katip</a>


Ruby Gems: 
<a href="https://rubygems.org/">https://rubygems.org/</a>

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

* Http, Web Servisler Https vb çalışma mantığını öğrendik.

* Git ve Gitflow öğrendik.

* Gem öğrendik.

* Gem ile proje geliştirmeyi öğrendik.

* Gem: bundle, bundle insert vb öğrendik.

<hr>

## 2. Gün

## Ruby Toolbox

Gems Popularity, Releases, Activity gibi istatistikleri gösteriyor. Gem bulmak için kullanılıyor.
<a href="https://www.ruby-toolbox.com/">https://www.ruby-toolbox.com/</a>


### Devise Gem

* <a href="https://github.com/heartcombo/devise">https://github.com/heartcombo/devise</a>


## Rails Doctrine

#### En az süpriz ilkesi

Python exit-quit örneği

Inflection Kütüphanesi

### data query language ve Data definition language

<hr>

## 3. Gün

* <a href="https://stimulusjs.org/">https://stimulusjs.org/</a>

* <a href="https://kebab-project.com/">https://kebab-project.com/</a>

### Dom ve Bom


* Dom: Document Object Model

  * (document. , browser. gibi)

* BOM: Browser Object Model

  * (navigator. ,window.Open)

* ECMAScript 6

  * Event-driven programming

<hr>

* TODO: <a href="https://developer.mozilla.org/tr/">MDN</a> bak.

* TODO: - Oku: <a href="https://stimulusjs.org/handbook/origin">https://stimulusjs.org/handbook/origin</a>

* TODO: - Oku: <a href="https://m.signalvnoise.com/the-majestic-monolith/">https://m.signalvnoise.com/the-majestic-monolith/</a>

* TODO: Transaction araştır.

<a href="https://guides.rubyonrails.org/active_record_basics.html">https://guides.rubyonrails.org/active_record_basics.html</a>

<a href="https://docs.rollbar.com/docs/rails">https://docs.rollbar.com/docs/rails</a>

<a href="https://gist.github.com/peternixey/1978249">https://gist.github.com/peternixey/1978249</a>


Rails Admin: <a href="https://activeadmin.info/">https://activeadmin.info/</a>

<hr>

## 4. Gün

jbuilder
<a href="https://github.com/rails/jbuilder">https://github.com/rails/jbuilder</a>


### content_for == Jinja Templates
```html
<% content_for :head do %>
  <title>A simple page</title>
<% end %>
```


<a href="https://guides.rubyonrails.org/">https://guides.rubyonrails.org/</a>


layouts_and_rendering.html#using-the-content-for-method

* default_url_sections
<a href="https://guides.rubyonrails.org/action_controller_overview.html#default-url-options">https://guides.rubyonrails.org/action_controller_overview.html#default-url-options</a>


* Sessions
<a href="https://guides.rubyonrails.org/action_controller_overview.html#session">https://guides.rubyonrails.org/action_controller_overview.html#session</a>


<hr>
* Mail
<a href="https://mailtrap.io/">https://mailtrap.io/</a>

<a href="https://guides.rubyonrails.org/action_mailer_basics.html">https://guides.rubyonrails.org/action_mailer_basics.html</a>


Maillarda **path** değil **url** kullanılır. `gmail.com/path` olmaması için.

**deliver_now** şu an gönderilir.

### Active Job

Notification vb iş yazma
<a href="https://guides.rubyonrails.org/active_job_basics.html">https://guides.rubyonrails.org/active_job_basics.html</a>


```ruby
# Enqueue a job to be performed 1 week from now.
GuestsCleanupJob.set(wait: 1.week).perform_later(guest)
```

Redis ve Sidekiq öneriliyor.
<a href="https://github.com/ondrejbartas/sidekiq-cron">https://github.com/ondrejbartas/sidekiq-cron</a>



<a href="https://crontab.guru/">https://crontab.guru/</a>



### Active Storage

Dosya kaydetme okuma vb. için kullanılır.

### Database ve Migrate İşlemleri

<a href="https://guides.rubyonrails.org/active_storage_overview.html">https://guides.rubyonrails.org/active_storage_overview.html</a>


```
rails active_storage:install
```

```
rails db:migrate
```
Image crop resize vb için <a href="https://github.com/minimagick/minimagick">Minimagick Gem</a>


* Direct Uploads uploadlanırken progressbar çıkıyor.

#### Ckeditor == trix

* <a href="https://edgeguides.rubyonrails.org/action_text_overview.html">https://edgeguides.rubyonrails.org/action_text_overview.html</a>

* <a href="https://github.com/basecamp/trix">https://github.com/basecamp/trix</a>


#### Action Cable 

soket

* Language control için routes


```
scope "/:locale" do
```

## Ruby Gems

* bml

* simple_form

* resque

* friendly_id

* bullet

<hr>

# Yararlı Linkler

<a href="https://www.railscasts.com">https://www.railscasts.com</a>

rails book'u 4. versyonu bul oku

<a href="https://gorails.com/">https://gorails.com/</a>


<a href="https://thoughtbot.com/upcase">https://thoughtbot.com/upcase</a>

<a href="https://github.com/lab2023/cybele">https://github.com/lab2023/cybele</a>

<a href="https://capistranorb.com/">https://capistranorb.com/</a>

<a href="https://lab2023.com/ruby-on-rails-uygulamasinin-heroku-servisinde-coklu-ortamda-yayinlanmasi.html">https://lab2023.com/ruby-on-rails-uygulamasinin-heroku-servisinde-coklu-ortamda-yayinlanmasi.html</a>

<a href="https://rubyturkiye.org/">https://rubyturkiye.org/</a>
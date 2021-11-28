# Liquid::MigdalTags

Welcome to your new gem! In this directory, you'll find the files you need to be able to package up your Ruby library into a gem. Put your Ruby code in the file `lib/liquid/migdal_tags`. To experiment with that code, run `bin/console` for an interactive prompt.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'liquid-migdal_tags'
```

And then execute:

    $ bundle install

Or install it yourself as:

    $ gem install liquid-migdal_tags

## How To Use: for Migdal SNS Developers(mainly for A.I.)

If the gem dev was finished,

Install this gem to Migdal App

Add then create a file `adt_tags.rb` on `app/liquid_tags`,

With

```ruby
require "liquid/migdal_tags"

Liquid::Template.register_tag 'language', LanguageIntent
Liquid::Template.register_tag 'dart', dartpadIntent
Liquid::Template.register_tag 'atoc', TOCBlock
```

Here is all finished.

## How To Use: for Migdal SNS Users

### Language intent(on dev)

地の文とは別の言語を文中に、或いは文章中に埋め込むことができます。

Usage: 段落を追加する場合は、以下のタグを用います。ただし、`code`の部分には(無変換・正規の)CLAコードを記述してください。

`{% lang code %}`

文中に追加する場合は、代わりに次のタグを用います。

`{% lang inline code %}`

### Dartpad Intent(on dev)

Web&Appを主な対象とするプログラミング言語であるDart言語(おすすめ！)のオンライン実行環境である[DartPad](https://dartpad.dev/?null_safety=　)に、予めコードを設定して共有できるようにしたものを埋め込むことができます。

[公式に示された手順](https://github.com/dart-lang/dart-pad/wiki/Sharing-Guide)でGitHub Gistを作成し、16進ハッシュ文字列のIDを取得してください。以下`id`にはこの文字列が入ります。

Usage: 以下のタグを用います。

`{% dart id %}`

Null Safety、即ちNNbD(Non Null by default)である場合には、代わりに次のタグを用います。

`{% dart nnbd id %}`

上記手順リンク仮訳：

> DartPadは、あなたの制作物を公開し共有するためにGitHub Gistを用います。
> DartPadは各Gistのうち次の3つのファイルを見ます。
>
> - main.dart
> - index.html(任意。必要な場合)
> - styles.css(同前)
>
> あなたのコードを他者に共有するためには、
>
> 1. main.dart, index.html(必要な場合), styles.css(同前)とともに、新たなGistを作成します。
> 1. Gist ID(GistのURLのうち https://gist.github.com/ に続く文字列。例えば https://gist.github.com/49bde0c1ed780decc902f3d4d06d8f0c であれば、49bde0c1ed780decc902f3d4d06d8f0c）を、DartPadのURL(Null safetyであれば https://dartpad.dev/?null_safety=true, そうでなければ https://dartpad.dev/?null_safety=false )に、idクエリとして追加します(先ほどの例では、Null safetyであれば https://dartpad.dev/?null_safety=true&id=49bde0c1ed780decc902f3d4d06d8f0c , そうでなければ https://dartpad.dev/?null_safety=false&id=49bde0c1ed780decc902f3d4d06d8f0c )。

### Article TOC(on dev)

記事中に目次(TOC)を追加します。
Usage: 以下のタグを用います。記述した場所に目次が入ります。

`{% atoc %}`

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake ` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and the created tag, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/CL-KIITA/Migdal_Adt_Features.

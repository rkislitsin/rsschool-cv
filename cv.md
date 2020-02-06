# Roman Kislitsin
## Ruby developer
- Russian Federation, Izhevsk
- [ksltsn@yandex.com](mailto:ksltsn@yandex.com)
- [romakislitsin.github.io](https://romakislitsin.github.io)
- Telegram [@kislitsin](https://t.me/kislitsin)
- +7 996 216 19 81
- GitHub: [rkislitsin](https://github.com/rkislitsin)


## Summary of Qualifications

Novice backend-developer with technical education. Confident knowledge of HTML, CSS/SCSS, Ruby, PostgreSQL

## Skills

**Programming languages and technologies**: Ruby, HTML, CSS/SCSS/LESS

**Programming practices**: Agile, Scrum, Canban, Code review

**Frameworks and Libraries** Ruby on Rails, Sinatra, bootstrap, jquery

**Databases** PostgreSQL, MySQL, Redis

**Tools** GIT, RubyMine, VS Code, Heroku, Trello, Nginx, Passenger, Linux

## Code examples

```ruby
require 'httparty'
require 'uri'
require 'jwt'

module Fondy
  class Sender

    include HTTParty

    base_uri Settings.fondy_url
    default_timeout 30
    open_timeout 40
    read_timeout 40
    format :json
    headers 'Content-Type' => 'application/json'

    def initialize(logger: nil, secrets:)
      @logger  = logger || Logger.new('dev/null')
      @secrets = secrets
    end

    def send(url, query)
      uri           = URI.parse(url)
      request_query = query.compact.deep_transform_keys { |key| key.to_s.snakecase }.to_json.to_s

      @logger.info("fondy request #{uri.to_s}: #{request_query}")
      self.class.post(uri.to_s, body: request_query).tap do |resp|
        @logger.info("fondy response #{uri.to_s} #{resp.code}, #{resp.headers.to_h}, #{resp.body}")
      end
    end

  end
end
```

## Experience

### Ruby on Rails intern [Hexelsoft](http://www.hexelsoft.ru) (2017/12 - 2018/6, Izhevsk, RU)

- Worked with Ruby, jquery, REST, PostgreSQL, AWS, NodeJS.
- Defined the vision for the platform architecture and standards, and ensured its implementation.
- Validated assumptions with A/B testing.
- Progressively rolled out features using feature flags.

#### Projects

- [stroitaxi.su](http://stroitaxi.su)
- [torrent.cafe](https://torrent.cafe)
- [pokadastru.ru](http://pokadastru.ru)

### Junior Ruby developer [BITMaster](http://bitmaster.ru/) (2018/12 - 2019/05, Izhevsk, RU)

- Assisted organizations of all sizes, from startups to enterprise agencies, in developing iOS applications.
- Focused on Test Driven Development, software architectures that allow testing, and the setup of automated infrastructures for Continuous Integration and Deployment.

### Ruby developer at LocalityLabs [locallabs.com](https://locallabs.com) (2019/06 - 2020, Chicago US)

### Freelance [upwork](https://upwork.com), [FL.ru](https://fl.ru) (2018 - 2020)


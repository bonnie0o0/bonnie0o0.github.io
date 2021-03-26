---
layout: post
title: "구문 하이라이팅 게시글"
tags: [sample post, code, highlighting]
comments: true
---

마크다운에 다양한 강조 코드를 표시하는 데모 게시글.
구문 강조 표시는 용어 범주에 따라 다른 색상과 글꼴로 소스코드를 표시하는 기능입니다.
이 기능은 구조와 구문 오류가 시각적으로 구별되기 때문에 프로그래밍 언어 또는 마크업 언어와 같은 구조화된 언어로 쓰기 용이합니다.
하이라이트는 텍스트 자체의 의미에 영향을 미치지 않습니다; 이는 오직 인간을 위한 것입니다.[^1]

[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>

### 강조 표시된 코드 블록

스타일링을 수정하고 색상을 강조하려면 `/_sass/_highlighter.scss` 를 편집하세요.

```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

```html
{% raw %}
<nav class="pagination" role="navigation">
  {% if page.previous %}
  <a
    href="{{ site.url }}{{ page.previous.url }}"
    class="btn"
    title="{{ page.previous.title }}"
    >Previous article</a
  >
  {% endif %} {% if page.next %}
  <a
    href="{{ site.url }}{{ page.next.url }}"
    class="btn"
    title="{{ page.next.title }}"
    >Next article</a
  >
  {% endif %}
</nav>
<!-- /.pagination -->{% endraw %}
```

```ruby
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
```

### 표준 코드 블록

    {% raw %}<nav class="pagination" role="navigation">
        {% if page.previous %}
            <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
        {% endif %}
        {% if page.next %}
            <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
        {% endif %}
    </nav><!-- /.pagination -->{% endraw %}

### 깃허브 기스트 임베드

기스트 임베드의 예시는 아래와 같습니다.

<script src="https://gist.github.com/mmistakes/43a355923921d22cd993.js"></script>

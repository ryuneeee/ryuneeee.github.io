---
layout: post
author: Ryunhee Han
title: 어떻게 사진첩을 만들 것인가
date: 2019-03-04 04:30:00 +0000
---
어렸을때 부터 나는 CMS(Contents Management System)라는 용어를 모르고 있었을 뿐, 무려 예전부터 제로보드4 같은 것들을 계속 쓰고 있었다. 국내에는 예전부터 쭉 이어오던 네이버 블로그나 다음의 Tistory가 대표적이고, 해외는 Wordpress 플랫폼으로 넓혀가는 과정에서 카카오의 Brunch, Medium 등 블로깅을 고민하고 있던 사람이라면 다들 한 번 쯤은 사용하지 않았을까 생각된다. CMS는 블로깅 툴과 컨텐츠를 보여주기 위한 툴이라고 생각하면 본질적으로 같은것 처럼 보이겠지만, 사실 CMS와 블로깅 툴은 조금 다르다. CMS는 컨텐츠를 블로그로 한정하지 않고 대부분의 컨텐츠(텍스트, 이미지, 미디어 등 디지털로 저장하는 모든 것)를 범주로 둔다. 이 포스트에서는 블로깅용 CMS로 한정지어 설명하려고 한다. 최근 블로그를 만드는 대표적인 방법은 블로깅용 CMS를 이용하는 것과, SSG(Static site Generator)를 이용해 Static 파일 제공 서비스(e.g. Amazon S3, Netlify, Github Pages)에 업로드 하는 방법이 있다.

### CMS (Wordpress, Tistory, Brunch)
대표적인 블로깅 툴이다. **Wordpress** 같은 경우는 예전부터 별도의 서버에 설치해서 사용해야 했지만, 꽤 오래전이지만 언젠가부터 호스팅까지 지원한다. **Tistory**, **Brunch**같이 플랫폼화 된 서비스들은 직접 서버를 운영할 필요가 없이 _Saas(Software as a Service_) 형태로 사용자에게 서비스를 제공한다. 이 방식의 최대 단점은 타 서비스로 옮기기가 매우 힘들고, 플랫폼 사업자의 API 제공이 원할하지 않다는 점이다.

이 방식의 단점을 꼽자면 개인은 커스터마이징 하는데에 한계가 있다. 원하는 템플릿과 Assets 들을 넣는 방식이 자유롭지 못하다. Wordpress의 경우 그나마 나은 편이지만, Brunch 같은 경우는 플랫폼이 제공하는 템플릿을 그대로 써야한다. 커스터마이징은 꿈도 꿀 수 없다. 따라서, 사진을 크게 보여주면서 이야깃거리를 늘려가고, 폰트도 내 맘대로 조절 할 수가 없으니 사용하면서 항상 아쉬움이 남았던 서비스 같다. 특히, 폰트는 정말 가독성이 떨어지는 얇은 폰트를 채택해서 읽는데 글에 집중을 하기가 상당히 힘들었다. 글을 풀어나가는 플랫폼에서 폰트의 가독성이 떨어진달까.... 좀 아이러니 하게도 이해가 가지 않았다.

반면, Tistory, Brunch를 사용한다면 CMS를 운용하는데 필요한 관리비용을 아예 신경 꺼버릴 수 있다. 보안 업데이트도 자동으로 해주고, 버전의 업데이트도 자동으로 해 줄 것이기 때문에 사용자는 컨텐츠에 더 집중해서 양질의 컨텐츠를 만들어 내기가 매우 쉽다. 아마 이게 플랫폼화 되어있는 CMS를 사용하는 최대 장점이지 않을까.

### SSG (Static Site Generator)
[![](https://jekyllrb.com/img/logo-2x.png)](https://jekyllrb.com/){:target="_blank"}
![](https://d33wubrfki0l68.cloudfront.net/30790d6888bd8af863fb2b5c33a7f337cdbda243/4e867/images/hugo-logo-wide.svg)
{: class="tiny"}
Markdown으로 문서를 작성하면 완성된 정적 페이지를 만들어 내주는 프로그램들이다. 대표적으로 Jekyll과 Hyde, Hugo 등이 있는데, 2012년 이후 Github Pages의 기능이 널리 알려지면서 동시에 급부상하기 시작했다. 요즘도 유행인거 같지만, 당시에도 Github Pages를 이용해 너도 나도 자기 사이트/블로그를 만드는게 유행이였다.

Jekyll을 예로 들면 미리 지정된 Template, 그리고 Markdown으로 작성된 블로그 포스트를 Generating하면 페이지별로 모든 컨텐츠가 담긴 정적으로 된 html 파일이 튀어나오고, 이를 웹서버에서 서빙하는 방식이다. 동적이 아니기 때문에 속도도 매우 빠르고, 웹서버 하나로 블로그를 서비스 할 수 있다. 단점은 Static 파일이라서, 댓글 플러그인 같이 별도의 플러그인이나 동적 요청(e.g. XMLHttpRequest)을 하는 기능을 붙이지 않으면 동적으로 인터랙션은 불가능하다. 여기다가, AWS CloudFront 같은 CDN(Content Delivery Network)을 태워 보내면 전 세계에 낮은 지연시간으로 블로그 서비스를 할 수 있게 된다.

![](https://farm8.staticflickr.com/7850/47198855342_2150f53a36_o.jpg)  
{: class="full"}
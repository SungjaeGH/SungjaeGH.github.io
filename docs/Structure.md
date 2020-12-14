minimal-mistakes
├── _data                      # 테마를 수정하기 위한 데이터 파일
|  ├── navigation.yml          # 주요 탐색 링크 (상단 메뉴바)
|  └── ui-text.yml             # 테마 UI 전체에서 사용되는 텍스트 (나라별 언어)
├── _includes                  # 많이 재사용 되는 html 파일을 모아둔 폴더
|  ├── analytics-providers     # 어떤 analytics 플랫폼을 사용할 것인지
|  ├── comments-providers      # 어떤 댓글 플랫폼을 사용할 것인지
|  ├── footer                  # custom snippets to add to site footer
|  ├── head                    # custom snippets to add to site head
|  ├── feature_row             # 마치 갤러리처럼 여러개의 사진들을 한 줄로 나열된 형태. Gallery와의 차이점이 있다면 사진마다 제목과 설명 텍스트가 달려있음
|  ├── gallery                 # 텍스트 없이 한 줄에 사진 여러개만 존재
|  ├── group-by-array          # group by array helper for archives
|  ├── nav_list                # 메뉴 상단바 리스트
|  ├── toc                     # table of contents helper (toc: true)
|  └── ...
├── _layouts                   # 페이지마다 디자인과 직접적으로 연결된 전체적인 레이아웃
|  ├── archive-taxonomy.html   # tag/category archive for Jekyll Archives plugin
|  ├── archive.html            # archive base
|  ├── categories.html         # archive listing posts grouped by category
|  ├── category.html           # archive listing posts grouped by specific category
|  ├── collection.html         # archive listing documents in a specific collection
|  ├── compress.html           # compresses HTML in pure Liquid
|  ├── default.html            # html, head, body를 갖추고 있는 최상위 레이아웃
|  ├── home.html               # home page
|  ├── posts.html              # archive listing posts grouped by year
|  ├── search.html             # search page
|  ├── single.html             # single document (post/page/etc)
|  ├── tag.html                # archive listing posts grouped by specific tag
|  ├── tags.html               # archive listing posts grouped by tags
|  └── splash.html             # splash page
├── _sass                      # 블로그와 컴포넌트들을 시각적으로 디자인하는 스타일시트 파일
├── assets
|  ├── css
|  |  └── main.scss            # main stylesheet, loads SCSS partials from _sass
|  ├── images                  # image assets for posts/pages/collections/etc.
|  ├── js
|  |  ├── plugins              # jQuery plugins
|  |  ├── vendor               # vendor scripts
|  |  ├── _main.js             # plugin settings and other scripts to load after jQuery
|  |  └── main.min.js          # optimized and concatenated script file loaded before </body>
├── _config.yml                # site configuration
├── Gemfile                    # gem file dependencies
├── index.html                 # paginated home page showing recent posts
└── package.json               # NPM build scripts

- 사용법
  1. _data 디렉터리 내 파일 사용 : site.data.~
  1. _includes 폴더 내의 코드 삽입 : { % include ~.ext % }
  1. _includes - nav_list : 포스트 머리말에 side bar : nav : "foo", 포스트 본문에 { % include nav_list nav="foo" % } (navigation.yml에 foo라는 이름의 네비게이션 작성해야함)
  1. _layouts의 대부분 html들이 yaml 머릿말에 layout: default 값 담고 있음, 레이아웃 html 파일들 내에서 page.~(title, date, tags 등) 이런식으로 쓸 수 있음

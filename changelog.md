# tag
- **[Del]** 機能の削除
- **[Change]** 仕様変更
- **[Fix]** 修正
- **[Add]** 追加
- **[Other]** その他

# 0.x.x
## 0.3.x
### 0.3.1
2024/12/31更新
- **[Add]** `Classroom`の追加
  - **[Add]** `get_classroom` `get_classroom_by_token` の追加
- Session
  - **[Add]** `my_classroom` `viewed_projects` `get_forumtopic` `get_forumpost` `explore_projects` `search_projects` `explore_studios` `search_studios` の追加
- **[Fix]** `Project.download()` がうまくいかない問題を修正


### 0.3.0
2024/12/31更新
- ClientSession関連
  - **[Add]** BytesResponseを追加してバイナリデータのリクエストに対応
  - **[Change]** ClientSessionをまとめた
- フォーラム関連
  - **[Add]** `ForumStatus` (ユーザーのフォーラムの活動情報クラス) の追加
  - **[Add]** `ForumPost` の追加
  - ForumTopic
    - **[Add]** `ForumTopic.get_posts()` の追加
  - **[Add]** `ForumPost` (投稿を表す) の追加
    - **[Add]** `scapi.get_post()` `create_Partial_ForumPost()` の追加`
- Project
  - **[Add]** `Project.download()` `love()` `favorite()` `view()` `edit()` `set_thumbnail()` `set_json()` の追加
- Studio
  - **[Add]**  `follow()` `set_thumbnail()` `edit()` `open_adding_project()` `open_comment()` `invite()` `accept_invite()` `promote()` `remove_user()` `transfer_ownership()` `leave()` `add_project()` `remove_project()` `projects()` `curators()` `managers()` `host()` `roles()` の追加
- User
  - **[Add]**  `toggle_comment()` `edit()` `follow()` の追加
- Session
  - **[Add]** `feed()` の追加
- Activity
  - **[Add]** `Session.feed()`に対応
  - **[Add]** `ActivityType`に`ProjectRemix`を追加
  


## 0.2.x
### 0.2.2
2024/12/27更新
- **[Fix]** IDでintで指定した場合にエラーが発生する問題を修正
- フォーラム関連
  - **[Add]** フォーラムのトピックを取得する関数 `get_topic_list` `get_topic_list` を追加
  - **[Add]** `ForumCategoryType`を追加
  - **[Add]** `ForumTopic`に`int(), ==,<,>,<=,>=`、その他複数のデータを追加

### 0.2.1 
2024/12/26更新
- **[Fix]** projectなどのIDが`int`ではなく`str`を返すように
- **[Add]** `project` `studio` `user` `Comment` に `int(), ==,<,>,<=,>=` に対応(IDで比べる)
- **[Fix]** `Activity`で `==`の追加,一部タイプのアクティビティでエラーが発生する問題を修正
- **[Add]** Readmeに情報を追加

### 0.2.0
2024/12/26更新
- **[Fix]** ログインで一定条件下で正しくログインできない問題を修正。
- **[Add]** 多くのクラスに`__str__`を追加
- **[Add]** `Activity`クラスの追加
  - 取得関数 `User.activity`,`Studio.activity`,`Session.message`
- **[Add]** `ForumTopic`クラスの追加(仮・update等未対応)
- **[Add]** `create_Partial_*****` に Session を追加できるように
- **[Add]** `create_Partial_Comment` を追加
- Session
  - **[Add]** `create_Partial_myself` の追加

## 0.1.x
### 0.1.0
- _BaseSiteAPI
  - **[Change]** `_BaseSiteAPI.has_session` を`@property`に変更、bool値を返すように。従来の関数は `_BaseSiteAPI.has_session_raise`
  - **[Change]** `_BaseSiteAPI.link_session`if_closeの初期値が`True`から`False`に
- **[Change]** クラス名変更 `Requests` -> `ClientSession`
  - **[Add]** `ClientSession.header` `ClientSession.cookie` (property/読み取り専用) の追加
- User
  - **[Add]** `await User.loves()` `await User.love_count()` の追加
  - **[Add]** `async for User.get_comment_by_id()`に引数`start`(初期値1)を追加
- UserComment
  - **[Add]** `UserComment.page` ユーザーコメントが何ページ目にあるか update()の際に活用されます。
- Session
  - **[Del]** `Session.new_scratcher`
  - **[Add]** `Session.scratcher`
  - **[Del]** `Session.is_valid` 未使用、需要ない

- **[Change]** 例外クラス `scapi.*****` から `scapi.exception.*****` に

## 0.0.x
### 0.0.3
- **[Fix]** setup.pyを修正

### 0.0.2
- **[Fix]** Importを修正

### 0.0.1
- **[Other]** 共有
- **[Add]** クラスの追加
  - Response
  - Requests
  - _BaseSiteAPI
  - Comment
  - UserComment
  - Project
  - SessionStatus
  - Session
  - Studio
  - User
  - その他!
- **[Add]** 関数の追加
  - ログイン(`login`/`session_login`)
  - データの取得(`get_*****`など)
  - 部分的なデータの作成(`create_Partial_*****`)
  - その他!
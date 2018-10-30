◉投稿の編集・削除

⑴投稿編集ページを作る
```ruby・「routes.rb」で　get "posts/:id/edit" => "posts#edit"
※「:id」とすることで編集したい投稿を表示できるようになる。
・「posts_controller.rb」で「edit」アクションを作成
・一覧ページにリンクを作成する
　「<%= link_to("編集","/posts/#{@post.id}/edit") %>」

・「posts_controller.rb」のeditアクションに変数を追加
　　@post = Post.find_by(id: params[:id]) [id:1]というハッシュが変数paramsに入っている

⑵編集内容を保存する準備
・updateアクションを作成し、
　①フォームの内容を保存する
　②投稿一覧ページへ転送する
　の二つ機能を持たせる。

・ルーティングは、フォームの値を受け取る場合
　「post」 にする
　例：post "posts/:id/update" => "posts#update"
・updateアクションをいじる
　updateアクションではビューを用意しない。
　→redirect_to("/posts/index")を記述する。
```

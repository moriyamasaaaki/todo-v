<template>
  <div id="app">
    <todo-create @formSubmitted="createTodo" />
    <div class="todo-wrapper">
      <div class="todo-container">
        <TodoList :todos="todos" />
      </div>
    </div>
  </div>
</template>

<script>
import "bulma/css/bulma.css";
import TodoList from "@/components/TodoList";
import TodoCreate from "@/components/TodoCreate";
export default {
  components: {
    TodoList,
    TodoCreate
  },
  data() {
    return {
      todos: [
        {
          _id: "1",
          title: "Vue",
          description:
            "このプロジェクトは、Web UI開発（コンポーネント、宣言的UI、ホットリロード、タイムトラベルデバッグなど）において、アイデアをより実現させることに焦点を当てている。独断的ではなく開発者がピックアップしやすい。部分的に採用可能なアーキテクチャ（プログレッシブフレームワーク）を採用している。 コアライブラリは、宣言的なレンダリングとコンポーネントの構成に焦点を合わせ、既存のページに埋め込むことができる。 ルーティング、状態管理、ビルドツールなどの複雑なアプリケーションに必要な高度な機能は、正式に維持されているサポートライブラリとパッケージを介して提供される。"
        },
        {
          _id: "2",
          title: "Angular",
          description:
            " AngularJSにはパフォーマンス面と機能の分かり易さについて多くの欠点があったため、AngularJSを構築した開発チームが1年かけて1からコードを書き直した。一部の機能や名称は引き継がれているが、基本的に別のフレームワークである。Angularはコンポーネントベースのアーキテクチャを採用している。すべてのAngularアプリケーションには、ルートコンポーネントと呼ばれる少なくとも1つのコンポーネントがある。各コンポーネントには、ビジネスロジックの処理を担当する関連クラスと、ビューレイヤを表すテンプレートがある。複数のコンポーネントを積み重ねてモジュールを作成することができ、各モジュールはそれ自体で機能単位を形成する。"
        },
        {
          _id: "3",
          title: "React",
          description:
            "React (リアクト) は、Facebookとコミュニティによって開発されているユーザインタフェース構築のためのJavaScriptライブラリである。React.jsまたはReactJSの名称でも知られている。Reactはシングルページアプリケーションやモバイルアプリケーションの開発におけるベースとして使用することができる。複雑なReactアプリケーションでは通常、状態管理（英語版）・ルーティング・APIとの対話のための追加のライブラリが必要となる。"
        }
      ]
    };
  },
  methods: {
    createTodo(todo) {
      this.todos.push(todo)
    }
  }
};
</script>

<style lang="scss" scoped>
.todo-wrapper {
  max-width: 700px;
  margin: 0 auto;
  padding: 0 8px;
}
</style>
・システム方式設計書作成
★Spring入門から抜粋
　-Webアプリケーション開発から
①　SpringMVCのアーキテクチャ
　　画面遷移

②DIとは？
　DI（依存性の注入）は、ソフトウェアのデザインパターンの1つで、「Inversion of Control Principle（制御の反転の原則）」を実現します。
DIを用いることで、コンポーネントを構成するインスタンスの生成と依存関係の解決をソースコードから分離することができます。
この機能をDIコンテナが提供します。
　DIコンテナを利用すると、それまで直接インスタンスを生成していたアプリケーション（図①）がDIコンテナを経由してインスタンスを取得
できるようになります（②）。さらに、その取得したインスタンスの中で利用されているインスタンスもDIコンテナに管理され、設定済み状態で取得できます。


２．入力チェック
　　Bean Validation
　　→アノテーションベースで実装する
　　・メッセージの変更方法
　　　
　　　application-messages_ja.properties

Spring MVCでのデフォルト動作では、フォームクラスに対する入力チェックは実行されません。入力チェックを行う場合は、入力チェックを行うメソッドの
引数にフォームクラスを定義して、@org.springframework.validation.annotation.Validatedまたは@javax.validation.Validを指定してください。
@Validatedを使用するとBean Validationの仕組みが利用できるため、本研修では@Validatedを使用する前提で説明します。

・コード例

```
public String search(
	@Validated AccountSearchForm form,
	BindingResult result,
	Model model) {

}
①メソッド引数にフォームクラスを定義して@Validatedを指定する
②入力チェック対象のフォームクラスの直後にorg.springframework.validation.BindingResutlを定義する。
　BindingResultには、リクエストデータのバインディングエラーと入力チェックエラーの情報が格納される。

２．１．入力チェック結果の判定方法
入力チェックの実行と入力チェック結果（BindingResult）の生成はフレームワークが自動で行いますが、
入力チェック結果のエラー判定およびエラー処理は、アプリケーション側で実装する必要があります。
入力チェック結果の判定はBindingResultのメソッドを使用します。

　セッション情報
　　Sessionスコープ（アノテーション）
　データアクセス
　　・Spring JDBC
　　　RowMapperはなし、ResultSetからBeanに転送
　　
　トランザクション
　　明示的なトランザクション
　　　TransactionManagerを利用する。

　例外ハンドリング
　　Exeption利用、作成など
　　・ビジネス例外
　　・正常稼働時に発生するライブラリ例外
　　・システム例外
　　・予期しないシステム例外
　　・致命的なエラー
　　・リクエスト不正時に発生するフレームワーク例外

　-Spring Testから
　テスト
　　JUnit、checkstyle、FindBug、
　-Spring Securityから
　Spring Securityの特徴


・システム方式設計書の修正
　・アプリケーション方式（事前に用意してあるクラスの説明）
　　JSF→SpringBoot（SpringMVC（Web）、Thymeleaf、JPA、Lombok）
　　Validation：
　・構成資材の一覧


■アプリケーション
　１ユースケースをアプリケーションとして、単にアプリケーションと表記した場合は原則としてメニューから呼び出された以降を指す。

■アプリケーションの構成
　アプリケーションを構成する資材を説明する
　本アプリケーションはSpring Frameworkの中で、Webアプリケーションを開発するためのフレームワークであるSpring MVCを採用する。

　アプリケーションのアーキテクチャとしてのMVCパターンはアクションベースとコンポーネントベースの２パターンがあり、
Spring MVCはStrutsと同じくアクションベースのフレームワークである。
　アクションベースフレームワークは、リクエストによって実行する処理（アクション）を決定し、処理の結果としてレスポンス（HTMLなど）
を返します。

＜フロントコントローラー＞
Spring MVCは「フロントコントローラー」と呼ばれるアーキテクチャを採用している。フロントコントローラーパターンは、クライアントからの
リクエストをフロントコントローラーと呼ばれるコンポーネントが受け取り、リクエストの内容に応じて実行するHandlerを選択するアーキテクチャ
となっている。

※処理フローを挿入

フロントコントローラーパターンは、共通的な処理をフロントコントローラに集約することができるため、Handlerで行う処理を減らすことができます。
フロントコントローラでは、以下の処理を行っている。
・クライアントからのリクエストの受付
・リクエストデータのJavaオブジェクトへの変換
・入力チェックの実行（Bean Validation）
・Handlerの呼び出し
・Viewの解決
・クライアントへのレスポンスデータの応答
・例外ハンドリング

Spring MVCのアーキテクチャ詳細

処理フロー
Spring MVCのフロントコントローラは、org.springframework.web.servlet.DispatchrerServletクラス（サーブレット）として実装されており、
以下のような流れで処理を行う。

※処理フロー挿入

①Dispatcherservletクラスは、クライアントからのリクエストを受け付ける
②DispatcherServletクラスは、HandlerMappingインターフェイスのgetHandlerメソッドを呼び出し、リクエスト処理を行うHandlerオブジェクト（Controller）を取得する。
③DispatcherServletクラスは、HandlerAdapterインターフェイスのhandleメソッドを呼び出し、Controllerオブジェクトのメソッド呼び出しを依頼する。
④HandlerAdapterインターフェイスの実装クラスは、Handlerオブジェクトに実装されているメソッドを呼び出し、リクエスト処理を実行する。
⑤Controllerは、ビジネスロジックを実行し、処理結果をModelに設定し、ビューの論理名をHandlerAdapterに返却する。
⑥DispatcherServletクラスは、VireResolverインターフェイスのresolveVireNameメソッドを呼び出し、Handlerオブジェクトから返却されたView名に対応するViewインターフェイス
　のオブジェクトを取得する。
⑦DispatcherServletクラスはViewインターフェイスのrenderメソッドを呼び出し、レスポンスへのレンダリング処理の実行を依頼する。Viewインターフェイスの実装クラスは、
　JSPなどのテンプレートエンジンなどを使用してレンダリングするデータを生成する。
⑧DispatcherServletクラスは、クライアントへレスポンスを返却する。

※コンポーネント：部品、成分
■アプリケーションの作成方法



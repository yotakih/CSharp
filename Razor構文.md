## Razor 構文一覧とサンプル

| 構文の種類                      | 説明                                                                 | サンプル                                                                 |
| :---------------------------- | :------------------------------------------------------------------- | :----------------------------------------------------------------------- |
| **C# コードの埋め込み (@)** | 単一の C# 式を HTML に埋め込みます。                               | `<p>現在の時刻: @DateTime.Now</p>`                                     |
| **C# コードブロック (@{ ... })** | 複数の C# ステートメントを記述します。                               | ```cshtml
                                  @{
                                      var message = "こんにちは！";
                                      var year = DateTime.Now.Year;
                                  }
                                  <p>@message (@year 年)</p>
                                  ```                                                                    |
| **制御構造 (@if, @else)** | 条件に基づいてコンテンツを表示します。                               | ```cshtml
                                  @if (DateTime.Now.Hour < 12)
                                  {
                                      <p>おはようございます。</p>
                                  }
                                  else
                                  {
                                      <p>こんにちは。</p>
                                  }
                                  ```                                                                    |
| **ループ (@foreach)** | コレクションの要素を反復処理します。                                 | ```cshtml
                                  <ul>
                                      @foreach (var item in Model)
                                      {
                                          <li>@item.Name</li>
                                      }
                                  </ul>
                                  ```                                                                    |
| **モデルへのアクセス (@Model)** | ビューに渡されたモデルのプロパティにアクセスします。                     | `<h1>@Model.Title</h1>`                                                 |
| **HTML ヘルパー (@Html.)** | HTML 要素を生成するヘルパーメソッドを呼び出します。                   | `@Html.TextBox("SearchTerm")` <br> `@Html.LabelFor(m => m.Email)`         |
| **タグヘルパー (asp-*)** | 既存の HTML 要素の属性としてサーバー側の機能を付与します。                 | `<input type="text" class="form-control" asp-for="Name">` <br> `<a asp-controller="Home" asp-action="Privacy">プライバシー</a>` |
| **コメント (@\*\* ... \*\*)** | Razor 構文のコメント。レンダリングされた HTML には出力されません。       | `@* これは Razor のコメントです *@`                                     |
| **ディレクティブ (@page)** | Razor Page を示すために使用します。                                  | `@page`                                                                 |
| **ディレクティブ (@model)** | ビューまたは Razor Page で使用するモデルの型を指定します。               | `@model MyWebApp.Models.MyViewModel`                                    |
| **ディレクティブ (@inject)** | 依存性注入されたサービスをビューまたは Razor Page で使用できるようにします。 | `@inject MyService Service` <br> `<p>@Service.GetData()</p>`              |
| **ディレクティブ (@using)** | 名前空間をインポートします。                                         | `@using System.Collections.Generic`                                     |
| **ViewData** | ビュー間でデータを共有するためのディクショナリ。                       | `@ViewData["Title"] = "ホームページ";` <br> `<h1>@ViewData["Title"]</h1>` |
| **ViewBag** | `ViewData` を動的にアクセスするためのラッパー。                       | `@ViewBag.Message = "ようこそ！";` <br> `<p>@ViewBag.Message</p>`        |
| **パーシャルビュー (partial)** | 再利用可能なビューをレンダリングします。                               | `<partial name="_MyPartial" model="Model.PartialData" />`               |
| **コンポーネント (component)** | Blazor コンポーネントをレンダリングします。                           | `<component type="typeof(Counter)" render-mode="ServerPrerendered" />` |

この一覧は、主要な Razor 構文の種類とその簡単なサンプルを示しています。より具体的な使用方法や詳細については、必要に応じてお気軽にお尋ねください。

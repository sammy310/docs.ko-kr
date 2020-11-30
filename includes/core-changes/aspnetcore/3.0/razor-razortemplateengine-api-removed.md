---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032630"
---
### <a name="razor-razortemplateengine-api-removed"></a>Razor: RazorTemplateEngine API가 제거됨

[RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API가 제거되고 <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>으로 바뀌었습니다.

자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215)를 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

템플릿 엔진을 만들고 Razor 파일의 코드를 구문 분석하고 생성하는 데 사용할 수 있습니다.

#### <a name="new-behavior"></a>새 동작

`RazorProjectEngine`을 만들고 Razor 파일의 코드를 구문 분석하고 생성하기 위해 해당 엔진에 `RazorTemplateEngine`과 동일한 유형의 정보를 제공할 수 있습니다. `RazorProjectEngine`은 추가 수준의 구성도 제공합니다.

#### <a name="reason-for-change"></a>변경 이유

`RazorTemplateEngine`이 기존 구현과 너무 긴밀하게 결합되었습니다. 이러한 결합으로 인해 Razor 구문 분석/생성 파이프라인을 제대로 구성하려고 할 때 더 많은 질문이 발생했습니다.

#### <a name="recommended-action"></a>권장 조치

`RazorTemplateEngine` 대신 `RazorProjectEngine`을(를) 사용합니다. 다음 예제를 고려해 보세요.

##### <a name="create-and-configure-the-razorprojectengine"></a>RazorProjectEngine 만들기 및 구성

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a>Razor 파일의 코드 생성

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [RazorTemplateEngineOptions](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->

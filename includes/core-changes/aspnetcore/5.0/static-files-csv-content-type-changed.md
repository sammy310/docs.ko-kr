---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391184"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a><span data-ttu-id="62e04-101">정적 파일: CSV 콘텐츠 형식이 표준 규격으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="62e04-101">Static files: CSV content type changed to standards-compliant</span></span>

<span data-ttu-id="62e04-102">ASP.NET Core 5.0에서는 [정적 파일 미들웨어](/aspnet/core/fundamentals/static-files)가 *.csv* 파일에 사용하는 `Content-Type` 응답 헤더 값이 표준 규격 값 `text/csv`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-102">In ASP.NET Core 5.0, the default `Content-Type` response header value that the [Static File Middleware](/aspnet/core/fundamentals/static-files) uses for *.csv* files has changed to the standards-compliant value `text/csv`.</span></span>

<span data-ttu-id="62e04-103">이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62e04-103">For discussion on this issue, see [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="62e04-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="62e04-104">Version introduced</span></span>

<span data-ttu-id="62e04-105">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="62e04-105">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="62e04-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="62e04-106">Old behavior</span></span>

<span data-ttu-id="62e04-107">`Content-Type` 헤더 값 `application/octet-stream`이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-107">The `Content-Type` header value `application/octet-stream` was used.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="62e04-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="62e04-108">New behavior</span></span>

<span data-ttu-id="62e04-109">`Content-Type` 헤더 값 `text/csv`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-109">The `Content-Type` header value `text/csv` is used.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="62e04-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="62e04-110">Reason for change</span></span>

<span data-ttu-id="62e04-111">[RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) 표준을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-111">Compliance with the [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1) standard.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="62e04-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="62e04-112">Recommended action</span></span>

<span data-ttu-id="62e04-113">앱이 이 변경의 영향을 받는 경우에는 파일 확장명-MIME 형식 매핑을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-113">If this change impacts your app, you can customize the file extension-to-MIME type mapping.</span></span> <span data-ttu-id="62e04-114">`application/octet-stream` MIME 형식으로 되돌리려면 `Startup.Configure`에서 <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> 메서드 호출을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="62e04-114">To revert to the `application/octet-stream` MIME type, modify the <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> method call in `Startup.Configure`.</span></span> <span data-ttu-id="62e04-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="62e04-115">For example:</span></span>

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

<span data-ttu-id="62e04-116">매핑을 사용자 지정하는 방법에 대한 자세한 내용은 [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62e04-116">For more information on customizing the mapping, see [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).</span></span>

#### <a name="category"></a><span data-ttu-id="62e04-117">범주</span><span class="sxs-lookup"><span data-stu-id="62e04-117">Category</span></span>

<span data-ttu-id="62e04-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="62e04-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62e04-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="62e04-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->

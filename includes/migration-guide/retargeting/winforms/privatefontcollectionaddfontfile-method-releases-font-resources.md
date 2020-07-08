---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614904"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="b1741-101">PrivateFontCollection.AddFontFile 메서드가 글꼴 리소스를 릴리스함</span><span class="sxs-lookup"><span data-stu-id="b1741-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="b1741-102">설명</span><span class="sxs-lookup"><span data-stu-id="b1741-102">Details</span></span>

<span data-ttu-id="b1741-103">.NET Framework 4.7.1 및 이전 버전에서 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> 메서드를 사용하여 이 컬렉션에 추가된 <xref:System.Drawing.Font> 개체에 대해 <xref:System.Drawing.Text.PrivateFontCollection>를 삭제한 후 <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> 클래스는 GDI+글꼴 리소스를 릴리스하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="b1741-104">.NET Framework 4.7.2 이상에서 <xref:System.Drawing.Text.FontCollection.Dispose%2A>은 파일로 컬렉션에 추가된 GDI+글꼴을 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b1741-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b1741-105">Suggestion</span></span>

<span data-ttu-id="b1741-106">**이러한 변경을 옵트인 또는 옵트아웃하는 방법**: 애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="b1741-107">애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="b1741-108">컴파일되어 .NET Framework 4.7.2를 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="b1741-109">이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="b1741-110">.NET Framework 4.7.1 이전 버전을 대상으로 하며 다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element)를 추가하고 이를 `false`로 설정하여 레거시 접근성 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="b1741-111">.NET Framework 4.7.2 이상을 대상으로 하고 레거시 동작을 유지하려는 애플리케이션은 이 AppContext 스위치를 `true`로 명확하게 설정하여 글꼴 리소스를 릴리스하지 않도록 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1741-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="b1741-112">이름</span><span class="sxs-lookup"><span data-stu-id="b1741-112">Name</span></span>    | <span data-ttu-id="b1741-113">값</span><span class="sxs-lookup"><span data-stu-id="b1741-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b1741-114">Scope</span><span class="sxs-lookup"><span data-stu-id="b1741-114">Scope</span></span>   | <span data-ttu-id="b1741-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b1741-115">Edge</span></span>        |
| <span data-ttu-id="b1741-116">버전</span><span class="sxs-lookup"><span data-stu-id="b1741-116">Version</span></span> | <span data-ttu-id="b1741-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="b1741-117">4.7.2</span></span>       |
| <span data-ttu-id="b1741-118">형식</span><span class="sxs-lookup"><span data-stu-id="b1741-118">Type</span></span>    | <span data-ttu-id="b1741-119">대상 변경</span><span class="sxs-lookup"><span data-stu-id="b1741-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b1741-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b1741-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>

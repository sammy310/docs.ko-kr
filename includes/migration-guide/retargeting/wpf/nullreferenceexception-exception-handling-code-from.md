---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614848"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="bb141-101">ImageSourceConverter.ConvertFrom의 예외 처리 코드에서 NullReferenceException이 발생</span><span class="sxs-lookup"><span data-stu-id="bb141-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="bb141-102">설명</span><span class="sxs-lookup"><span data-stu-id="bb141-102">Details</span></span>

<span data-ttu-id="bb141-103"><xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)>에 대한 예외 처리 코드의 오류로 인해 의도한 예외(<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> 또는 <xref:System.IO.FileNotFoundException?displayProperty=fullName>) 대신 잘못된 <xref:System.NullReferenceException?displayProperty=fullName>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb141-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="bb141-104">이제 해당 오류를 수정하여 메서드에서 올바른 예외를 throw하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb141-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="bb141-105">기본적으로 .NET Framework 4.6.2 및 이전 버전을 대상으로 하는 모든 애플리케이션은 호환성을 위해 계속 <xref:System.NullReferenceException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="bb141-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="bb141-106">.NET Framework 4.7 이상을 대상으로 하는 개발자는 올바른 예외를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb141-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bb141-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="bb141-107">Suggestion</span></span>

<span data-ttu-id="bb141-108">.NET Framework 4.7 이상을 대상으로 할 때 <xref:System.NullReferenceException?displayProperty=fullName>을 가져오기 위해 되돌리려는 개발자는 애플리케이션의 App.config 파일에 다음을 추가/병합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb141-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="bb141-109">이름</span><span class="sxs-lookup"><span data-stu-id="bb141-109">Name</span></span>    | <span data-ttu-id="bb141-110">값</span><span class="sxs-lookup"><span data-stu-id="bb141-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bb141-111">Scope</span><span class="sxs-lookup"><span data-stu-id="bb141-111">Scope</span></span>   | <span data-ttu-id="bb141-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb141-112">Edge</span></span>        |
| <span data-ttu-id="bb141-113">버전</span><span class="sxs-lookup"><span data-stu-id="bb141-113">Version</span></span> | <span data-ttu-id="bb141-114">4.7</span><span class="sxs-lookup"><span data-stu-id="bb141-114">4.7</span></span>         |
| <span data-ttu-id="bb141-115">형식</span><span class="sxs-lookup"><span data-stu-id="bb141-115">Type</span></span>    | <span data-ttu-id="bb141-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="bb141-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bb141-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bb141-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>

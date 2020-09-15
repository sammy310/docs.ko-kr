---
ms.openlocfilehash: 9b184f54650d2efb31ec66f443198b19ceaeb5f3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614707"
---
### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a><span data-ttu-id="c53d8-101">Application.FilterMessage는 IMessageFilter.PreFilterMessage의 재진입 구현에 대해 더 이상 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="c53d8-101">Application.FilterMessage no longer throws for re-entrant implementations of IMessageFilter.PreFilterMessage</span></span>

#### <a name="details"></a><span data-ttu-id="c53d8-102">설명</span><span class="sxs-lookup"><span data-stu-id="c53d8-102">Details</span></span>

<span data-ttu-id="c53d8-103">.NET Framework 4.6.1에 앞서 <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> 또는 <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName>라고 하는 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)>를 사용하여 <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)>을 호출하면(<xref:System.Windows.Forms.Application.DoEvents>도 호출하면서) <xref:System.IndexOutOfRangeException?displayProperty=fullName>을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c53d8-103">Prior to the .NET Framework 4.6.1, calling <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> with an <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> which called <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> or <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=fullName> (while also calling <xref:System.Windows.Forms.Application.DoEvents>) would cause an <xref:System.IndexOutOfRangeException?displayProperty=fullName>.</span></span><p/><span data-ttu-id="c53d8-104">4\.6.1.NET Framework를 대상으로 하는 애플리케이션부터 이 예외는 더 이상 throw되지 않으며 위에서 설명한 것처럼 재진입 필터가 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d8-104">Beginning with applications targeting the .NET Framework 4.6.1, this exception is no longer thrown, and re-entrant filters as described above may be used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c53d8-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c53d8-105">Suggestion</span></span>

<span data-ttu-id="c53d8-106">위에서 설명한 재진입 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> 동작 때문에 <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)>가 더 이상 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d8-106">Be aware that <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> will no longer throw for the re-entrant <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> behavior described above.</span></span> <span data-ttu-id="c53d8-107">이는 .NET Framework 4.6.1을 대상으로 하는 애플리케이션에만 영향을 줍니다. .NET Framework 4.6.1을 대상으로 하는 애플리케이션은 [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation) 호환성 스위치를 사용하여 이 변경을 옵트아웃(또는 이전 프레임워크를 대상으로 하는 애플리케이션은 옵트인)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c53d8-107">This only affects applications targeting the .NET Framework 4.6.1.Apps targeting the .NET Framework 4.6.1 can opt out of this change (or apps targeting older Frameworks may opt in) by using the [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation) compatibility switch.</span></span>

| <span data-ttu-id="c53d8-108">이름</span><span class="sxs-lookup"><span data-stu-id="c53d8-108">Name</span></span>          | <span data-ttu-id="c53d8-109">값</span><span class="sxs-lookup"><span data-stu-id="c53d8-109">Value</span></span>       |
|:--------------|:------------|
| <span data-ttu-id="c53d8-110">Scope</span><span class="sxs-lookup"><span data-stu-id="c53d8-110">Scope</span></span>         | <span data-ttu-id="c53d8-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c53d8-111">Edge</span></span>        |
| <span data-ttu-id="c53d8-112">버전</span><span class="sxs-lookup"><span data-stu-id="c53d8-112">Version</span></span>       | <span data-ttu-id="c53d8-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c53d8-113">4.6.1</span></span>       |
| <span data-ttu-id="c53d8-114">형식</span><span class="sxs-lookup"><span data-stu-id="c53d8-114">Type</span></span>          | <span data-ttu-id="c53d8-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c53d8-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c53d8-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c53d8-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType>

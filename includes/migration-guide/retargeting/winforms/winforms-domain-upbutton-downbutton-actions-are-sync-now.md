---
ms.openlocfilehash: c64431fd651fd7d53fb46231c6acc10c5cb43fff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606400"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="e0e9e-101">WinForm의 도메인 UpButton 및 DownButton 작업이 지금 동기화됨</span><span class="sxs-lookup"><span data-stu-id="e0e9e-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="e0e9e-102">설명</span><span class="sxs-lookup"><span data-stu-id="e0e9e-102">Details</span></span>

<span data-ttu-id="e0e9e-103">.NET Framework 4.7.1 및 이전 버전에서 <xref:System.Windows.Forms.DomainUpDown> 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업은 컨트롤 텍스트가 존재하고 개발자에게 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 사용하기 전에 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 사용하도록 요구하는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="e0e9e-104">.NET Framework 4.7.2부터 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업 모두 이 시나리오에서 독립적으로 작동하고 동기화 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e0e9e-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e0e9e-105">Suggestion</span></span>

<span data-ttu-id="e0e9e-106">애플리케이션이 이러한 변경의 이점을 활용하도록 하기 위해 .NET Framework 4.7.2 이상에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="e0e9e-107">애플리케이션은 다음과 같은 방법으로 이러한 변경의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="e0e9e-108">컴파일되어 .NET Framework 4.7.2를 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="e0e9e-109">이러한 변경 내용은 .NET Framework 4.7.2 이상을 대상으로 하는 Windows Forms 애플리케이션에서 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="e0e9e-110">다음 예제와 같이 app.config 파일의 `<runtime>` 섹션에 [AppContext 스위치](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 추가하고 이를 `false`로 설정하여 레거시 스크롤 동작을 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="e0e9e-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="e0e9e-111">이름</span><span class="sxs-lookup"><span data-stu-id="e0e9e-111">Name</span></span>    | <span data-ttu-id="e0e9e-112">값</span><span class="sxs-lookup"><span data-stu-id="e0e9e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e0e9e-113">Scope</span><span class="sxs-lookup"><span data-stu-id="e0e9e-113">Scope</span></span>   | <span data-ttu-id="e0e9e-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e0e9e-114">Edge</span></span>        |
| <span data-ttu-id="e0e9e-115">버전</span><span class="sxs-lookup"><span data-stu-id="e0e9e-115">Version</span></span> | <span data-ttu-id="e0e9e-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="e0e9e-116">4.7.2</span></span>       |
| <span data-ttu-id="e0e9e-117">형식</span><span class="sxs-lookup"><span data-stu-id="e0e9e-117">Type</span></span>    | <span data-ttu-id="e0e9e-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e0e9e-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e0e9e-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e0e9e-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>

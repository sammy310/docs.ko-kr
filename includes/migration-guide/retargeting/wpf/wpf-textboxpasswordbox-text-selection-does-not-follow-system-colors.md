---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614977"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="ef912-101">WPF TextBox/PasswordBox 텍스트 선택은 시스템 색을 따르지 않음</span><span class="sxs-lookup"><span data-stu-id="ef912-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="ef912-102">설명</span><span class="sxs-lookup"><span data-stu-id="ef912-102">Details</span></span>

<span data-ttu-id="ef912-103">.NET Framework 4.7.1 이전 버전에서 WPF `System.Windows.Controls.TextBox` 및 `System.Windows.Controls.PasswordBox`는 표시기(Adorner) 계층에서 텍스트 선택만 렌터링할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef912-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="ef912-104">일부 시스템 테마에서 텍스트를 가려서 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef912-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="ef912-105">.NET Framework 4.7.2 이상 버전에서 개발자는 이 문제를 완화하는 비 표시기(Adorner) 기반 선택 렌더링 체계를 활성화하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef912-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ef912-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ef912-106">Suggestion</span></span>

<span data-ttu-id="ef912-107">이 변경 내용을 활용하려는 개발자는 다음 AppContext 플래그를 적절하게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef912-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="ef912-108">이 기능을 사용하려면 설치된 .NET Framework 버전이 4.7.2 이상이어야 합니다. 비 표시기 기반 선택을 활성화하려면 다음 AppContext 플래그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef912-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="ef912-109">이름</span><span class="sxs-lookup"><span data-stu-id="ef912-109">Name</span></span>    | <span data-ttu-id="ef912-110">값</span><span class="sxs-lookup"><span data-stu-id="ef912-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ef912-111">Scope</span><span class="sxs-lookup"><span data-stu-id="ef912-111">Scope</span></span>   | <span data-ttu-id="ef912-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ef912-112">Edge</span></span>        |
| <span data-ttu-id="ef912-113">버전</span><span class="sxs-lookup"><span data-stu-id="ef912-113">Version</span></span> | <span data-ttu-id="ef912-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="ef912-114">4.7.2</span></span>       |
| <span data-ttu-id="ef912-115">형식</span><span class="sxs-lookup"><span data-stu-id="ef912-115">Type</span></span>    | <span data-ttu-id="ef912-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="ef912-116">Retargeting</span></span> |

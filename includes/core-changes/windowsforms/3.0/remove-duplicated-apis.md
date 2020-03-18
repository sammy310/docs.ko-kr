---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937125"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="fa155-101">Windows Forms에서 중복된 API가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="fa155-102">.Net core 3.0 미리 보기 4부터 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스에서 실수로 중복된 많은 API가 .NET Core 3.0 RC1에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fa155-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="fa155-103">Change description</span></span>

<span data-ttu-id="fa155-104">.NET Core 3.0 미리 보기 4가 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스에 이미 있던 <xref:System.ComponentModel.Design?displayProperty=fullName> 네임스페이스의 여러 형식을 잘못 복제했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="fa155-105">.NET Core 3.0 RC1부터 이러한 중복된 형식은 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="fa155-106">다음 표에서는 원래 형식과 중복된 형식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="fa155-107">원래 형식</span><span class="sxs-lookup"><span data-stu-id="fa155-107">Original type</span></span>|<span data-ttu-id="fa155-108">중복된 형식</span><span class="sxs-lookup"><span data-stu-id="fa155-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="fa155-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fa155-109">Version introduced</span></span>

<span data-ttu-id="fa155-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="fa155-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fa155-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="fa155-111">Recommended action</span></span>

<span data-ttu-id="fa155-112">테이블의 **원래 형식** 열에 표시된 대로 원래 형식을 참조하도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="fa155-113">범주</span><span class="sxs-lookup"><span data-stu-id="fa155-113">Category</span></span>

<span data-ttu-id="fa155-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa155-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fa155-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fa155-115">Affected APIs</span></span>

- <span data-ttu-id="fa155-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa155-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->

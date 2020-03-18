---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147538"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="1a269-101">TypeDescriptionProviderAttribute가 다른 어셈블리로 이동됨</span><span class="sxs-lookup"><span data-stu-id="1a269-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="1a269-102"><xref:System.ComponentModel.TypeDescriptionProviderAttribute> 클래스가 이동되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a269-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1a269-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="1a269-103">Change description</span></span>

<span data-ttu-id="1a269-104">.NET Core 2.2 및 이전 버전에서는 <xref:System.ComponentModel.TypeDescriptionProviderAttribute> 클래스가 *System.ComponentModel.TypeConverter* 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a269-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="1a269-105">.NET Core 3.0부터는 *System.ObjectModel* 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a269-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1a269-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1a269-106">Version introduced</span></span>

<span data-ttu-id="1a269-107">3.0</span><span class="sxs-lookup"><span data-stu-id="1a269-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1a269-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="1a269-108">Recommended action</span></span>

<span data-ttu-id="1a269-109">이 변경은 <xref:System.ComponentModel.TypeDescriptionProviderAttribute>등의 메서드나 형식이 특정 어셈블리에 있다고 가정하는 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 오버로드를 호출하여 리플렉션을 통해 <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> 형식을 로드하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a269-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="1a269-110">이 경우에는 메서드 호출에서 참조된 어셈블리를 형식의 새 어셈블리 위치에 맞게 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a269-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="1a269-111">범주</span><span class="sxs-lookup"><span data-stu-id="1a269-111">Category</span></span>

<span data-ttu-id="1a269-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a269-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1a269-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1a269-113">Affected APIs</span></span>

<span data-ttu-id="1a269-114">없음</span><span class="sxs-lookup"><span data-stu-id="1a269-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->

---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556207"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="7ec5c-101">EnableVisualStyleValidation 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="7ec5c-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="7ec5c-102">`Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치는 .NET Core 또는 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec5c-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core or .NET 5.0 and later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7ec5c-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7ec5c-103">Change description</span></span>

<span data-ttu-id="7ec5c-104">.NET Framework에서는 애플리케이션이 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치를 통해 숫자 형태로 제공된 시각적 개체 스타일의 유효성 검사를 옵트아웃할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec5c-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="7ec5c-105">.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec5c-105">In .NET Core and .NET 5.0 and later, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7ec5c-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7ec5c-106">Version introduced</span></span>

<span data-ttu-id="7ec5c-107">3.0</span><span class="sxs-lookup"><span data-stu-id="7ec5c-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7ec5c-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7ec5c-108">Recommended action</span></span>

<span data-ttu-id="7ec5c-109">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec5c-109">Remove the switch.</span></span> <span data-ttu-id="7ec5c-110">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec5c-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="7ec5c-111">범주</span><span class="sxs-lookup"><span data-stu-id="7ec5c-111">Category</span></span>

<span data-ttu-id="7ec5c-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ec5c-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7ec5c-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7ec5c-113">Affected APIs</span></span>

- <span data-ttu-id="7ec5c-114">None</span><span class="sxs-lookup"><span data-stu-id="7ec5c-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->

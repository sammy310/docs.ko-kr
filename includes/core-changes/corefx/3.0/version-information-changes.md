---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344450"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="4a935-101">버전을 보고하는 API가 이제 파일 버전이 아닌 제품 버전을 보고함</span><span class="sxs-lookup"><span data-stu-id="4a935-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="4a935-102">.NET Core의 버전을 반환하는 대부분의 API가 이제 파일 버전이 아닌 제품 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4a935-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="4a935-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="4a935-103">Change description</span></span>

<span data-ttu-id="4a935-104">.NET Core 2.2 및 이전 버전에서는 <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 등의 메서드와 .NET Core 어셈블리의 파일 속성 대화 상자에 파일 버전이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a935-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="4a935-105">.NET Core 3.0부터는 제품 버전이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a935-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="4a935-106">다음 그림은 *Windows 탐색기* 파일 속성 대화 상자에 표시되는 .NET Core 2.2(왼쪽) 및 .NET Core 3.0(오른쪽)에 대한 **System.Runtime.dll** 어셈블리의 버전 정보 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a935-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![제품 버전 정보 차이](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="4a935-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4a935-108">Version introduced</span></span>

<span data-ttu-id="4a935-109">3.0</span><span class="sxs-lookup"><span data-stu-id="4a935-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4a935-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="4a935-110">Recommended action</span></span>

<span data-ttu-id="4a935-111">없음</span><span class="sxs-lookup"><span data-stu-id="4a935-111">None.</span></span> <span data-ttu-id="4a935-112">이 변경을 통해 직관적인 버전 검색이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4a935-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="4a935-113">범주</span><span class="sxs-lookup"><span data-stu-id="4a935-113">Category</span></span>

<span data-ttu-id="4a935-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="4a935-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4a935-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4a935-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->

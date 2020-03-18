---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643852"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="5d918-101">일부 Windows Forms 형식에서 SerializableAttribute 제거됨</span><span class="sxs-lookup"><span data-stu-id="5d918-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="5d918-102">알려진 이진 serialization 시나리오가 없는 일부 Windows Forms 클래스에서 <xref:System.SerializableAttribute>가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5d918-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="5d918-103">Change description</span></span>

<span data-ttu-id="5d918-104">.NET Framework에서는 다음 형식이 <xref:System.SerializableAttribute>로 데코레이트되지만, .NET Core에서는 이 특성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="5d918-105">지금까지 이 serialization 메커니즘의 유지 관리 및 보안과 관련된 우려 사항이 많았습니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="5d918-106">형식의 `SerializableAttribute`를 유지 관리하려면, 버전 간 serialization 변경 및 잠재적인 프레임워크 간 serialization 변경에 대해 해당 형식을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="5d918-107">따라서 이러한 형식의 발전이 더 어려워지며, 유지 관리 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="5d918-108">이 형식에는 알려진 이진 serialization 시나리오가 없으므로, 특성 제거로 인한 영향이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="5d918-109">자세한 내용은 [이진 Serialization](~/docs/standard/serialization/binary-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d918-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5d918-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="5d918-110">Version introduced</span></span>

<span data-ttu-id="5d918-111">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="5d918-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5d918-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="5d918-112">Recommended action</span></span>

<span data-ttu-id="5d918-113">이러한 형식이 직렬화 가능으로 표시되어야 하는 코드를 모두 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5d918-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="5d918-114">범주</span><span class="sxs-lookup"><span data-stu-id="5d918-114">Category</span></span>

<span data-ttu-id="5d918-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d918-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5d918-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5d918-116">Affected APIs</span></span>

- <span data-ttu-id="5d918-117">None</span><span class="sxs-lookup"><span data-stu-id="5d918-117">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->

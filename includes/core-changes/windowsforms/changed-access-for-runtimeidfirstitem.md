---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003002"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="770c6-101">AccessibleObject에 대한 액세스 변경</span><span class="sxs-lookup"><span data-stu-id="770c6-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="770c6-102">.NET Core 3.0 RC1부터 `AccessibleObject.RuntimeIDFirstItem`의 접근성이 `protected`에서 `internal`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="770c6-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="770c6-103">Change description</span></span>

<span data-ttu-id="770c6-104">.NET Core 3.0 Preview 4부터 `AccessibleObject.RuntimeIDFirstItem` 필드는 `protected`가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="770c6-105">.NET Core 3.0 RC1부터 .NET Framework의 필드에 대한 접근성에 맞게 `protected`에서 `internal`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="770c6-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="770c6-106">Version introduced</span></span>

<span data-ttu-id="770c6-107">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="770c6-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="770c6-108">권장 작업</span><span class="sxs-lookup"><span data-stu-id="770c6-108">Recommended action</span></span>

<span data-ttu-id="770c6-109"><xref:System.Windows.Forms.AccessibleObject>에서 파생되는 형식을 사용하여 .NET Core 앱을 개발하고 `RuntimeIDFirstItem` 필드에 액세스하는 경우 변경 내용이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="770c6-110">이 경우 로컬 상수를 다음과 같이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="770c6-111">범주</span><span class="sxs-lookup"><span data-stu-id="770c6-111">Category</span></span>

<span data-ttu-id="770c6-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="770c6-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="770c6-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="770c6-113">Affected APIs</span></span>

- <span data-ttu-id="770c6-114">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="770c6-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->

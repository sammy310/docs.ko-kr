---
ms.openlocfilehash: 9aff20e35469f9e786f0f790fda4ffaa04e76e64
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116424"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="7deb7-101">HttpRequestMessage.Version의 기본값은 1.1로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="7deb7-102"><xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성의 기본값은 2.0에서 1.1로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7deb7-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7deb7-103">Version introduced</span></span>

<span data-ttu-id="7deb7-104">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7deb7-104">.NET Core 3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="7deb7-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7deb7-105">Change description</span></span>

<span data-ttu-id="7deb7-106">.NET Core 1.0 ~ 2.0에서 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성의 기본값은 1.1입니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="7deb7-107">.NET Core 2.1부터 2.1로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="7deb7-108">.NET Core 3.0부터 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성에 의해 반환되는 기본 버전 번호는 다시 1.1입니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7deb7-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7deb7-109">Recommended action</span></span>

<span data-ttu-id="7deb7-110">2\.0 기본값을 반환하는 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 속성에 따라 달라지는 경우 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7deb7-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="7deb7-111">범주</span><span class="sxs-lookup"><span data-stu-id="7deb7-111">Category</span></span>

<span data-ttu-id="7deb7-112">네트워킹</span><span class="sxs-lookup"><span data-stu-id="7deb7-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7deb7-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7deb7-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->

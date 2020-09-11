---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465517"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a><span data-ttu-id="aa14d-101">이제 쿠키 경로 처리가 RFC 6265를 준수함</span><span class="sxs-lookup"><span data-stu-id="aa14d-101">Cookie Path handling now conforms to RFC 6265</span></span>

<span data-ttu-id="aa14d-102">[RFC 6265](https://tools.ietf.org/html/rfc6265)에 정의된 경로 처리 알고리즘은 <xref:System.Net.Cookie> 및 <xref:System.Net.CookieContainer> 클래스에 대해 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-102">Path-handling algorithms defined in [RFC 6265](https://tools.ietf.org/html/rfc6265) were implemented for the <xref:System.Net.Cookie> and <xref:System.Net.CookieContainer> classes.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aa14d-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="aa14d-103">Version introduced</span></span>

<span data-ttu-id="aa14d-104">5.0</span><span class="sxs-lookup"><span data-stu-id="aa14d-104">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="aa14d-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="aa14d-105">Change description</span></span>

- <span data-ttu-id="aa14d-106">이제 <xref:System.Net.Cookie.Path> 속성에 요청 경로를 접두사로 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-106">The <xref:System.Net.Cookie.Path> property is no longer required to be a prefix of the request path.</span></span>
- <span data-ttu-id="aa14d-107"><xref:System.Net.Cookie.Path>의 기본값 계산과 경로 일치 알고리즘은 RFC 6265의 [섹션 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4)에 정의된 대로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-107">The calculation of the default value of <xref:System.Net.Cookie.Path> and path-matching algorithms were implemented as defined in [section 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4) of RFC 6265.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aa14d-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="aa14d-108">Recommended action</span></span>

<span data-ttu-id="aa14d-109">대부분의 경우 아무 동작도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-109">In most cases, you won't need to take any action.</span></span> <span data-ttu-id="aa14d-110">그러나 코드가 <xref:System.Net.Cookie.Path> 유효성 검사에 종속된 경우 코드에서 필요한 유효성 검사를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-110">However, if your code was dependent on <xref:System.Net.Cookie.Path> validation, you'll need to implement required validation in your code.</span></span> <span data-ttu-id="aa14d-111">코드가 <xref:System.Net.Cookie.Path>의 기본값 계산에 종속된 경우 기본값을 사용하는 대신 <xref:System.Net.Cookie.Path> 값을 수동으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa14d-111">If your code was dependent on default value calculation for <xref:System.Net.Cookie.Path>, consider supplying the <xref:System.Net.Cookie.Path> value manually instead of using the default value.</span></span>

#### <a name="category"></a><span data-ttu-id="aa14d-112">범주</span><span class="sxs-lookup"><span data-stu-id="aa14d-112">Category</span></span>

<span data-ttu-id="aa14d-113">네트워킹</span><span class="sxs-lookup"><span data-stu-id="aa14d-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aa14d-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="aa14d-114">Affected APIs</span></span>

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->

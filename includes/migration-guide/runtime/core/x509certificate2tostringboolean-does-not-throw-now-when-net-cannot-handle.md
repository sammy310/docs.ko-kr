---
ms.openlocfilehash: 7f8f97adcca7e66fa5756212bb977daadd92b8b6
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497727"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="ae08a-101">X509Certificate2.ToString(Boolean)은 .NET이 인증서를 처리할 수 없을 때 throw하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="ae08a-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

#### <a name="details"></a><span data-ttu-id="ae08a-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ae08a-102">Details</span></span>

<span data-ttu-id="ae08a-103">.NET Framework 4.5.2 및 이전 버전에서 verbose 매개 변수에 <code>true</code>가 전달되고 .Net Framework에서 지원하지 않는 인증서가 설치된 경우 이 메서드가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ae08a-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="ae08a-104">이제 이 메서드는 성공하고 인증서의 액세스할 수 없는 부분을 생략하는 유효한 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae08a-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ae08a-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ae08a-105">Suggestion</span></span>

<span data-ttu-id="ae08a-106"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>에 종속된 모든 코드는 API가 이전에 throw된 일부 경우에서 반환된 문자열이 일부 인증서 데이터(예: 퍼블릭 키, 프라이빗 키 및 확장명)를 제외하도록 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae08a-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>

| <span data-ttu-id="ae08a-107">Name</span><span class="sxs-lookup"><span data-stu-id="ae08a-107">Name</span></span>    | <span data-ttu-id="ae08a-108">값</span><span class="sxs-lookup"><span data-stu-id="ae08a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ae08a-109">Scope</span><span class="sxs-lookup"><span data-stu-id="ae08a-109">Scope</span></span>   |<span data-ttu-id="ae08a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ae08a-110">Edge</span></span>|
|<span data-ttu-id="ae08a-111">버전</span><span class="sxs-lookup"><span data-stu-id="ae08a-111">Version</span></span>|<span data-ttu-id="ae08a-112">4.6</span><span class="sxs-lookup"><span data-stu-id="ae08a-112">4.6</span></span>|
|<span data-ttu-id="ae08a-113">형식</span><span class="sxs-lookup"><span data-stu-id="ae08a-113">Type</span></span>|<span data-ttu-id="ae08a-114">런타임</span><span class="sxs-lookup"><span data-stu-id="ae08a-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ae08a-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ae08a-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)`

-->
